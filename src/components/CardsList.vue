<script>
import Card from "./Card.vue";
import AppLoader from "./AppLoader.vue";
import { store } from "../data/store";

export default {
  data() {
    return {
      store,
    };
  },
  components: {
    Card,
    AppLoader,
  },
};
</script>

<template>
  <div class="deck-container">
    <div class="n-results">found</div>

    <div
      class="row row-cols-5 m-0"
      v-if="!store.isPageLoading"
    >
      <Card />
    </div>
    <AppLoader v-else />
  </div>
</template>

<style lang="scss" scoped>
@use "../assets/styles.scss/variables.scss" as *;
@use "../assets/generals.scss" as *;
.deck-container {
  background-color: white;
  padding: 3rem;
  .n-results {
    background-color: $dark-color;
    font-weight: bold;
    color: white;
    padding: 2rem;
  }
}
</style>
