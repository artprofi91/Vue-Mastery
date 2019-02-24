<template>
  <div class="product">
    <ProductImage :imagePath="[imagePath]"></ProductImage>
    <ProductInfo @colorHover="onColorHover"></ProductInfo>
  </div>
</template>

<script>
import ProductImage from "./product-image/productImage.vue";
import ProductInfo from "./product-info/productInfo.vue";

export default {
  name: "Product",
  components: { ProductImage, ProductInfo },
  data() {
    return {
      imagePath: require("@/assets/green.png")
    };
  },
  methods: {
    onColorHover(imagePath) {
      this.imagePath = imagePath;
    }
  }
};
</script>

<style lang="scss">
@import "./product";
</style>
