<template>
  <v-app id="inspire">
    <v-navigation-drawer :mobile-breakpoint="768" v-model="drawer" app>
      <v-img
        class="pa-3 pt-4"
        height="150"
        src="mountains.jpg"
        gradient="to top right, rgba(19,84,122,.5), rgba(128,208,199,.8)"
      >
        <v-avatar size="70" class="mb-3">
          <img
            src="https://dvyvvujm9h0uq.cloudfront.net/com/articles/1525891879-886386-sam-burriss-457746-unsplashjpg.jpg"
            alt="Mawi"
          />
        </v-avatar>
        <div class="white--text text-subititle-1 font-weight-bold">
          Brian Mawira
        </div>
        <div class="white--text -text-subtitle-2">rodgers_B.R.Y</div>
      </v-img>

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

    <v-app-bar
      height="150"
      app
      color="primary"
      dark
      shrink-on-scroll
      src="mountains.jpg"
    >
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(19,84,122,.5), rgba(128,208,199,.8)"
        >
        </v-img>
      </template>

      <v-container class="pa-0 header-container">
        <v-row>
          <v-app-bar-nav-icon @click="drawer = !drawer" class="mt-2" />
          <v-spacer />
        </v-row>
        <v-row>
          <v-app-bar-title class="ml-4 text-h4">{{
            $store.state.appTitle
          }}</v-app-bar-title>
        </v-row>
        <v-row>
          <live-date-time />
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
    "live-date-time": require("./components/Tools/LiveDateTime.vue").default,
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

<style lang="sass">
.header-container
  max-width: none !important
</style>
