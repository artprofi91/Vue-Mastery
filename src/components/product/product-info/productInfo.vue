<template>
  <div class="product-info">
    <h2>{{ title }}</h2>
    <p v-if="inStock">
      In Stock
    </p>
    <p v-if="!inStock" :style="{ 'text-decoration': 'line-through' }">
      Out of Stock
    </p>
    <span v-if="onSale && inStock">On Sale!</span>
    <ul>
      <li v-for="detail in details" :key="detail.id">{{ detail.desc }}</li>
    </ul>
    <div
      v-for="(variant, index) in variants"
      :key="variant.variantId"
      class="color-box"
      :style="{ 'background-color': variant.variantColor }"
      @mouseover="updateProduct(index)"
    ></div>
    <ul>
      <li v-for="size in sizes" :key="size.id">{{ size.size }}</li>
    </ul>
    <button
      v-on:click="addToCart"
      :disabled="!inStock"
      :class="{ disabledButton: !inStock }"
    >
      Add to Cart
    </button>
  </div>
</template>

<script>
export default {
  name: "ProductInfo",
  data() {
    return {
      brand: "Vue Mastery",
      product: "Socks",
      onSale: true,
      selectedVariant: 0,
      details: [
        { desc: "80% cotton", id: 1 },
        { desc: "20% polyester", id: 2 },
        { desc: "Gender-neutral", id: 3 }
      ],
      variants: [
        {
          variantId: 111,
          variantColor: "green",
          variantImage: require("@/assets/green.png"),
          variantQuantity: 10
        },
        {
          variantId: 112,
          variantColor: "blue",
          variantImage: require("@/assets/blue.png"),
          variatnQuantity: 0
        }
      ],
      sizes: [
        { size: "S", id: 10 },
        { size: "M", id: 11 },
        { size: "L", id: 12 },
        { size: "XL", id: 13 },
        { size: "XXL", id: 14 }
      ],
      cart: 0
    };
  },
  methods: {
    addToCart: function() {
      this.cart += 1;
      this.$emit("addToCart", this.cart);
    },
    updateProduct(index) {
      this.selectedVariant = index;
      this.$emit("colorHover", this.imagePath);
    }
  },
  computed: {
    title() {
      return this.brand + " " + this.product;
    },
    imagePath() {
      return this.variants[this.selectedVariant].variantImage;
    },
    inStock() {
      return this.variants[this.selectedVariant].variantQuantity > 0
        ? true
        : false;
    }
  }
};
</script>

<style lang="scss">
@import "./productInfo";
</style>
