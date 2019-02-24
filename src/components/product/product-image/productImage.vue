<template>
  <div class="product-image">
    <img :src="imagePath" />
  </div>
</template>

<script>
export default {
  name: "ProductImage",
  props: ["imagePath"]
};
</script>

<style lang="scss">
@import "./productImage";
</style>
