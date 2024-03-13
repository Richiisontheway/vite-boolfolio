<script>
export default {
  data() {
    return {
      message: "sono main",
    };
  },
};
</script>

<template>
  <main>
    <h1>Titolo {{ message }}</h1>
  </main>
</template>

<style scoped>
header {
  color: aquamarine;
}
</style>
