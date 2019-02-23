<template>
  <div class="product-image">
    <img :src="image" />
  </div>
</template>

<script>
export default {
  name: "ProductImage",
  data() {
    return {
      image: require("@/assets/green.png")
    };
  }
};
</script>

<style lang="scss">
@import "./productImage";
</style>
