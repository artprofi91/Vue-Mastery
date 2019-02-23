<template>
  <div class="product-info">
    <h2>{{ product }}</h2>
  </div>
</template>

<script>
export default {
  name: "ProductInfo",
  data() {
    return {
      product: "Socks"
    };
  }
};
</script>

<style lang="scss">
@import "./productInfo";
</style>
