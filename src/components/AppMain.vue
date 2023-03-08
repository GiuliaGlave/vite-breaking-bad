<script>
import CardsList from "./CardsList.vue";
import { store } from "../data/store";
export default {
  data() {
    return {
      store,
      typeTitle: "",
    };
  },
  components: {
    CardsList,
  },
  emits: ["select-card-type"],

  methods: {
    selectType() {
      this.$emit("select-card-type", this.typeTitle);
    },
  },
};
</script>

<template>
  <section>
    <div class="container">
      <select
        name="type"
        id="type"
        class="p-2 m-3 rounded"
        v-model="typeTitle"
        @submit.prevent="$emit('select-card-type', typeTitle)"
      >
        <option
          v-for="singleType in store.cardTypes"
          value=""
        >
          {{ singleType }}
        </option>
      </select>
    </div>
    <div class="container">
      <CardsList />
    </div>
  </section>
</template>

<style lang="scss" scoped>
@use "../assets/styles.scss/variables.scss" as *;
section {
  background-color: $bg-color;
  select {
    width: 15rem;
  }
}
</style>
