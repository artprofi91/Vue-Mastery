<template>
  <div class="product">
    <ProductImage :imagePath="[imagePath]"></ProductImage>
    <ProductInfo
      @colorHover="onColorHover"
      @addToCart="onAddToCart"
    ></ProductInfo>
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
    },
    onAddToCart(event) {
      this.$emit("addToCart", event);
    }
  }
};
</script>

<style lang="scss">
@import "./product";
</style>
