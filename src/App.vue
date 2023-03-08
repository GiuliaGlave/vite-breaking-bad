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
      })
      .finally(() => {
        setTimeout(() => {
          store.isPageLoading = false;
        }, 1000);
      });
  },
  methods: {
    fetchCardType(type) {
      this.$emit("select-card-type");
    },
  },
};
/* `https://db.ygoprodeck.com/api/v7/cardinfo.php?type=${type}&num=15&offset=0` */
</script>

<template>
  <AppHeader />
  <AppMain @select-card-type="fetchCardType" />
</template>

<style lang="scss"></style>
