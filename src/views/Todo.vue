<template>
  <div class="home">
    <add-task-field />
    <list-tasks v-if="$store.state.tasks.length" />
    <no-tasks v-else />
  </div>
</template>

<script>
export default {
  components: {
    "add-task-field": require("@/components/Todo/AddTask.vue").default,
    "list-tasks": require("@/components/Todo/ListTask.vue").default,
    "no-tasks": require("@/components/Todo/NoTasks.vue").default,
  },
};
</script>


