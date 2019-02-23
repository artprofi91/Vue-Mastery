<template>
  <div class="product-info">
    <h2>{{ product }}</h2>
    <p v-if="inStock">In Stock</p>
    <p v-if="!inStock">Out of Stock</p>
    <span v-if="onSale && inStock">On Sale!</span>
  </div>
</template>

<script>
export default {
  name: "ProductInfo",
  data() {
    return {
      product: "Socks",
      inStock: false,
      onSale: true
    };
  }
};
</script>

<style lang="scss">
@import "./productInfo";
</style>
