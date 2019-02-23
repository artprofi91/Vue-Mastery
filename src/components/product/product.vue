<template>
  <div class="product">
    <ProductImage />
    <ProductInfo />
  </div>
</template>

<script>
import ProductImage from "./product-image/productImage.vue";
import ProductInfo from "./product-info/productInfo.vue";

export default {
  name: "Product",
  components: { ProductImage, ProductInfo }
};
</script>

<style lang="scss"></style>
