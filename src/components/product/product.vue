<template>
  <div class="product">
    <ProductImage :imagePath="[imagePath]"></ProductImage>
    <ProductInfo
      @colorHover="onColorHover"
      @addToCart="onAddToCart"
    ></ProductInfo>
    <div>
      <h2>Reviews</h2>
      <p v-if="!reviews.length">There are no reviews yet.</p>
      <ul>
        <li v-for="(review, index) in reviews" :key="index">
          <p>{{ review.name }}</p>
          <p>Rating: {{ review.rating }}</p>
          <p>{{ review.review }}</p>
        </li>
      </ul>
    </div>
    <ProductReview @reviewSubmitted="onReviewSubmitted" />
  </div>
</template>

<script>
import ProductImage from "./product-image/productImage.vue";
import ProductInfo from "./product-info/productInfo.vue";
import ProductReview from "./product-review/productReview.vue";

export default {
  name: "Product",
  components: { ProductImage, ProductInfo, ProductReview },
  data() {
    return {
      imagePath: require("@/assets/green.png"),
      reviews: []
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
    }
  }
};
</script>

<style lang="scss">
@import "./product";
</style>
