<script>
import axios from "axios";
import Card from "./Card.vue";

export default {
  data() {
    return {};
  },
  components: {
    Card,
  },
  created() {
    console.log(axios);
  },
};
</script>

<template>
  <Card />
</template>

<style lang="scss" scoped></style>
