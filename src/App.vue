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
    <header>header</header>
    <main>
        <h1>Titolo {{ message }}</h1>
    </main>
    <footer>
        Footer
    </footer>
</template>

<style scoped>
h1{
    color: blueviolet;
}
</style>
