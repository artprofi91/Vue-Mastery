<template>
  <div class="cart">
    <p>Cart({{ cart }})</p>
  </div>
</template>

<script>
export default {
  name: "Cart",
  props: ["cart"]
};
</script>

<style lang="scss">
@import "./cart";
</style>
