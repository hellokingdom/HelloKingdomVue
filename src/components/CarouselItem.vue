<template>
  <div>
    <div class="item">
      <a :href="item.link">{{item.category}}</a>
    </div>
  </div>
</template>

<script>
export default {
  name: "CarouselItem",
  props: ["item"]
};
</script>

<style lang="scss">
.item {
  display: block;
}
</style>
