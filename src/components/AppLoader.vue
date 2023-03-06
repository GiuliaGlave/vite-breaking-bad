<script>
export default {};
</script>

<template>
  <div class="loader">
    <slot></slot>
    <h2>Loading...</h2>
  </div>
</template>

<style lang="scss" scoped>
@use "../assets/styles.scss/variables.scss" as *;
@use "../assets/styles.scss/mixins.scss" as *;
.loader {
  @include flex-center();
  width: 100%;
  position: fixed;
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  background-color: rgba($color: #999, $alpha: 0.7);
  color: white;
  h2 {
    font-size: 4rem;
    color: $dark-color;
    font-weight: bold;
  }
}
</style>
