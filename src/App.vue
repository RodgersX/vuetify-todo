<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6"> Vuetify Todo </v-list-item-title>
          <v-list-item-subtitle> Best Todo Ever! </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item v-for="item in items" :key="item.title" link :to="item.to">
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app color="primary" dark shrink-on-scroll src="mountains.jpg">
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(19,84,122,.5), rgba(128,208,199,.8)"
        >
        </v-img>
      </template>

      <v-container class="pa-0">
        <v-row>
          <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
          <v-spacer />
        </v-row>
        <v-row>
          <v-app-bar-title class="mx-4">Vuetify Todo</v-app-bar-title>
        </v-row>
      </v-container>

      <search />
    </v-app-bar>

    <v-main>
      <!--  -->
      <v-container>
        <router-view />
        <snackbar />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import Search from "./components/Tools/Search.vue";
export default {
  components: {
    snackbar: require("@/components/Shared/Snackbar.vue").default,
    search: require("./components/Tools/Search.vue").default,
  },

  data() {
    return {
      drawer: null,

      items: [
        { title: "Todo", icon: "mdi-view-dashboard", to: "/" },
        { title: "About", icon: "mdi-help-box", to: "/about" },
      ],
    };
  },
};
</script>
