<template>
  <div id="app">
    <NavBar />
    <Cart :cart="cart" />
    <Product @addToCart="onAddToCart" />
  </div>
</template>

<script>
import NavBar from "./components/nav-bar/navBar.vue";
import Cart from "./components/cart/cart.vue";
import Product from "./components/product/product.vue";

export default {
  name: "app",
  components: { NavBar, Cart, Product },
  data() {
    return {
      cart: 0
    };
  },
  methods: {
    onAddToCart(event) {
      this.cart = event;
    }
  }
};
</script>

<style lang="scss">
@import "./sass/style";
</style>
