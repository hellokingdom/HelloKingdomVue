<template>
  <div class="form">
    <input v-model="categoryText" placeholder="Category">
    <input v-model="linkText" placeholder="Link">
    <button v-on:click="addItem()">Add item</button>
  </div>
</template>

<script>
export default {
  name: "AddCarouselItem",
  data() {
    return {
      categoryText: "",
      linkText: ""
    };
  },
  methods: {
    addItem() {
      const category = this.categoryText;
      const link = this.linkText;

      this.$emit("add-item", {
        category,
        link
      });
    }
  }
};
</script>

<style lang="scss" scoped>
.form {
  padding: 1em;
  margin: 1em;
  border: 1px dotted blue;
}
</style>
