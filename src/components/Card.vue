<script>
import { store } from "../data/store";

export default {
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <div
    class="col mb-4"
    v-for="card in store.cards"
  >
    <div class="card pb-2">
      <div v-for="img in card.card_images">
        <img
          :src="img.image_url"
          alt=""
          class="img-fluid"
        />
      </div>
      <div class="name">{{ card.name }}</div>
      <div class="archetype">{{ card.archetype }}</div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../assets/styles.scss/variables.scss" as *;
@use "../assets/generals.scss" as *;
.card {
  text-align: center;
  background-color: $bg-color;
  display: flex;
  height: 100%;

  .name {
    color: white;
    font-weight: bold;
    padding: 1rem;
    text-transform: uppercase;
  }
  .archetype {
  }
}
</style>
