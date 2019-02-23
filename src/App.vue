<template>
  <div id="app">
    <NavBar />
    <Product />
  </div>
</template>

<script>
import NavBar from "./components/nav-bar/navBar.vue";
import Product from "./components/product/product.vue";

export default {
  name: "app",
  components: { NavBar, Product }
};
</script>

<style lang="scss">
@import "./sass/style";
</style>
