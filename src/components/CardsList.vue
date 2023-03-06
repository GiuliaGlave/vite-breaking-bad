<script>
import axios from "axios";
import Card from "./Card.vue";

export default {
  data() {
    return {
      cards: [],
    };
  },
  components: {
    Card,
  },
  created() {
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0")
      .then((response) => {
        console.log(response); //in console guardo il percoso per accedere all'array con i dati che mi servono
        this.cards = response.data.data; //riscrivo il percorso
        console.log(this.cards);
      });
  },
};
</script>

<template>
  <Card />

  <div class="deck-container">
    <div class="n-results">found</div>
    <div class="deck row row-cols-5">
      <div
        v-for="card in cards"
        class="card col"
      >
        <div v-for="img in card.card_images">
          <img
            :src="img.image_url"
            alt=""
          />
        </div>
        <div class="name">{{ card.name }}</div>
        <div class="archetype">{{ card.archetype }}</div>
      </div>
    </div>
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
    color: white;
    padding: 2rem;
  }
  .deck {
    padding: 0;
    .card {
      text-align: center;
      background-color: $bg-color;
      padding: 0;
      display: flex;
      gap: 1rem;
      img {
        width: 100%;
      }
      .name {
        color: white;
        font-weight: 500;
      }
      .archetype {
      }
    }
  }
}
</style>
