<template>
  <div class="home">
    <add-task-field />
    <list-tasks v-if="$store.state.tasks.length" />
    <no-tasks v-else />

    <done-sorting v-if="$store.state.sorting" />
  </div>
</template>

<script>
export default {
  components: {
    "list-tasks": require("@/components/Todo/ListTask.vue").default,
    "no-tasks": require("@/components/Todo/NoTasks.vue").default,
    "done-sorting": require("../components/Todo/ButtonDoneSorting.vue").default,
  },
};
</script>
