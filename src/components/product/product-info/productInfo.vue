<template>
  <div class="product-info">
    <h2>{{ product }}</h2>
    <p v-if="inStock">In Stock</p>
    <p v-if="!inStock">Out of Stock</p>
    <span v-if="onSale && inStock">On Sale!</span>
    <ul>
      <li v-for="detail in details" :key="detail.id">
        {{ detail.desc }}
      </li>
    </ul>
    <div v-for="variant in variants" :key="variant.variantId">
      <p>{{ variant.variantColor }}</p>
    </div>
    <ul>
      <li v-for="size in sizes" :key="size.id">
        {{ size.size }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "ProductInfo",
  data() {
    return {
      product: "Socks",
      inStock: false,
      onSale: true,
      details: [
        { desc: "80% cotton", id: 1 },
        { desc: "20% polyester", id: 2 },
        { desc: "Gender-neutral", id: 3 }
      ],
      variants: [
        { variantId: 111, variantColor: "green" },
        { variantId: 112, variantColor: "blue" }
      ],
      sizes: [
        { size: "S", id: 10 },
        { size: "M", id: 11 },
        { size: "L", id: 12 },
        { size: "XL", id: 13 },
        { size: "XXL", id: 14 }
      ]
    };
  }
};
</script>

<style lang="scss">
@import "./productInfo";
</style>
