<template>
  <v-fab-transition>
    <v-btn
      @click="$store.commit('toggleSorting')"
      color="primary"
      class="done-sorting"
      fab
      dark
      
    >
      <v-icon>mdi-check</v-icon>
    </v-btn>
  </v-fab-transition>
</template>

<script>
export default {};
</script>

<style lang="sass">
.done-sorting
    position: fixed
    bottom: 20px
    left: 50%
    transform: translateX(-50%)
</style>
