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
    store.isPageLoading = true;
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0")
      .then((response) => {
        store.cards = response.data.data;
        console.log(store.cards);
      })
      .finally(() => {
        setTimeout(() => {
          store.isPageLoading = false;
        }, 1000);
      });
  },
};
</script>

<template>
  <AppHeader />
  <AppMain />
</template>

<style lang="scss"></style>
