<script>
export default {
  data() {
    return {
      message: "helo",
    };
  },
};
</script>

<template>
  <header>
    <h1>Titolo {{ message }}</h1>
  </header>
</template>

<style scoped>
header {
  color: aquamarine;
}
</style>
