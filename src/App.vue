<template>
  <div id="app">
    <Header />
    <Main />
  </div>
</template>

<script>
import Header from "./Header.vue";
import Main from "./Main.vue";

export default {
  name: "App",
  components: {
    Header,
    Main,
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
#app {
  background-color: #1E2D3B;
  height: 100vh;
}
</style>
