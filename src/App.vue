<template>
  <div id="app">
    <div class="nav-bar"></div>
    <Product />
  </div>
</template>

<script>
import Product from "./components/product/product.vue";

export default {
  name: "app",
  components: {
    Product
  }
};
</script>

<style lang="scss"></style>
