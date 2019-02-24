<template>
  <div class="tabs">
    <span
      class="tab"
      :class="{ activeTab: selectedTab === tab }"
      v-for="(tab, index) in tabs"
      :key="index"
      v-on:click="selectTab(tab)"
    >
      {{ tab }}
    </span>
    <div v-show="selectedTab === 'Reviews'">
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
  </div>
</template>

<script>
export default {
  name: "ProductTabs",
  props: ["reviews"],
  data() {
    return {
      tabs: ["Reviews", "Make a Review"],
      selectedTab: "Reviews"
    };
  },
  methods: {
    selectTab(tab) {
      this.selectedTab = tab;
      this.$emit("selectTab", this.selectedTab);
    }
  }
};
</script>

<style lang="scss">
@import "./productTabs";
</style>
