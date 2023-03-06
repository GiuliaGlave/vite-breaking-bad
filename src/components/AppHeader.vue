<script>
export default {
  data() {
    return {};
  },
};
</script>

<template>
  <header>
    <div>
      <img
        src="../assets/yugioh-logo.png"
        alt=""
      />
    </div>
    <h1>Yu-Gi-Oh Api</h1>
  </header>
</template>

<style lang="scss" scoped>
header {
  display: flex;
  align-items: center;
  height: 5rem;
  gap: 2rem;

  div {
    width: 10%;
    height: 100%;
    img {
      width: 100%;
      height: 100%;
      object-fit: contain;
      object-position: left;
    }
  }
}
</style>
