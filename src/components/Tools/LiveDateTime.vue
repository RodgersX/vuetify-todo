<template>
  <div class="ml-4 text-subtitle-1" v-text="date"></div>
</template>

<script>
import { format } from "date-fns";

export default {
  data() {
    return {
      date: "",
    };
  },

  mounted() {
    this.getDate();
  },

  methods: {
    getDate() {
      this.date = format(new Date(), "MMMM dd, H:mm:ss");
      setTimeout(this.getDate, 1000);
    },
  },
};
</script>

<style></style>
