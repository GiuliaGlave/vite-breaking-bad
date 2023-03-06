<script>
import CardsList from "./CardsList.vue";

export default {
  components: {
    CardsList,
  },
};
</script>

<template>
  <section>
    <div class="container">
      <select>
        <span>ss</span>
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
}
</style>
