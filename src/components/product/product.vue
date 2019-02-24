<template>
  <div class="product">
    <ProductImage :imagePath="[imagePath]"></ProductImage>
    <ProductInfo @colorHover="onColorHover" @addToCart="onAddToCart">
    </ProductInfo>
    <ProductTabs @selectTab="onSelectTab" :reviews="reviews"></ProductTabs>
    <ProductReview
      v-show="selectedTab !== 'Reviews'"
      @reviewSubmitted="onReviewSubmitted"
    ></ProductReview>
  </div>
</template>

<script>
import ProductImage from "./product-image/productImage.vue";
import ProductInfo from "./product-info/productInfo.vue";
import ProductReview from "./product-review/productReview.vue";
import ProductTabs from "./product-tabs/productTabs.vue";

export default {
  name: "Product",
  components: {
    ProductImage,
    ProductInfo,
    ProductReview,
    ProductTabs
  },
  data() {
    return {
      imagePath: require("@/assets/green.png"),
      reviews: [],
      selectedTab: "Reviews"
    };
  },
  methods: {
    onColorHover(imagePath) {
      this.imagePath = imagePath;
    },
    onAddToCart(event) {
      this.$emit("addToCart", event);
    },
    onReviewSubmitted(productReview) {
      this.reviews.push(productReview);
    },
    onSelectTab(event) {
      this.selectedTab = event;
    }
  }
};
</script>

<style lang="scss">
@import "./product";
</style>
