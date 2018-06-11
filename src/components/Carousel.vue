<template>
  <div class="hello">
    <carousel-item v-for="(item, index) in carousel" :key="index" :item.sync="item" ref="myItem"></carousel-item>
    <add-carousel-item v-on:add-item="addItem"></add-carousel-item>
    <button @click="onPrint">Print</button>
  </div>
</template>

<script>
import CarouselItem from "./CarouselItem";
import AddCarouselItem from "./AddCarouselItem";

export default {
  name: "Carousel",
  components: {
    AddCarouselItem,
    CarouselItem
  },
  methods: {
    addItem: function(item) {
      this.carousel.push(item);
    },
    onPrint() {
      this.$refs.myItem.forEach(function(value) {
        console.log(value.$el.innerHTML);
      });
    }
  },
  data() {
    return {
      carousel: [
        {
          category: "Fresh",
          link:
            "https://groceries.morrisons.com/webshop/getSearchProducts.do?clearTabs=yes&isFreshSearch=true&chosenSuggestionPosition=&entry=10000007353&ad=56740%7C1179316%7C67006%7C1179313"
        },
        {
          category: "Bakery & Cakes",
          link:
            "https://groceries.morrisons.com/webshop/getSearchProducts.do?clearTabs=yes&isFreshSearch=true&chosenSuggestionPosition=&entry=10000007353&ad=56740%7C1179316%7C67006%7C1179313"
        }
      ]
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
</style>
