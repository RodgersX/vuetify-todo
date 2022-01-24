<template>
  <v-text-field
    v-model="search"
    @focus="searchClosed = false"
    @blur="searchClosed = true"
    class="mt-1 expanding-search"
    :class="{ closed: searchClosed && !search }"
    placeholder="search"
    dense
    clearable
    prepend-inner-icon="mdi-magnify"
    filled
  ></v-text-field>
</template>

<script>
export default {
  data() {
    return {
      searchClosed: true,
      search: null,
    };
  },
};
</script>

<style lang="sass">
.expanding-search
    transition: max-width 0.3s

    .v-input__slot
        cursor: pointer !important
        &:before, &:after
            border-color: transparent !important

    &.closed
        max-width: 45px
        .v-input__slot
            background: transparent !important
</style>