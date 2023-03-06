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
  <div v-for="card in cards">
    {{ card.archetype }}
  </div>
</template>

<style lang="scss" scoped></style>
