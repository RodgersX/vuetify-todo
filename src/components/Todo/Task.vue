<template>
  <div>
    <v-list-item
      @click="doneTask(task.id)"
      :class="{ 'blue lighten-5': task.done }"
    >
      <template>
        <v-list-item-action>
          <v-checkbox :input-value="task.done" color="primary"></v-checkbox>
        </v-list-item-action>

        <v-list-item-content>
          <v-list-item-title
            :class="{ 'text-decoration-line-through': task.done }"
          >
            {{ task.title }}
          </v-list-item-title>
        </v-list-item-content>
        <v-list-item-action>
          <task-menu :task="task" />
        </v-list-item-action>
      </template>
    </v-list-item>

    <v-divider />
  </div>
</template>

<script>
export default {
  props: ["task"],
  components: {
    "task-menu": require("@/components/Todo/TaskMenu.vue").default,
  },

  methods: {
    doneTask(id) {
      this.$store.commit("doneTask", id);
    },
  },
};
</script>

<style></style>
