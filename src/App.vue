<script>
import axios from "axios";
import { store } from "./data/store";

import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

export default {
  data() {
    return {
      store,
    };
  },
  components: {
    AppHeader,
    AppMain,
  },
  created() {
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0")
      .then((response) => {
        store.cards = response.data.data;
        console.log(store.cards);
      });
  },
};
</script>

<template>
  <AppHeader />
  <AppMain />
</template>

<style lang="scss"></style>
