<template> 
  <h2>Re-usable Slot Cards</h2>
  <p>We create card-like div boxes from the foods array.</p>
  <p>We also create a card-like footer by reusing the same component.</p>
  <div class="wrapper">
    <food-item v-for="food in foods" :key="food.name">  
      <img v-bind:src="getImageUrl(food.url)" :alt="food.name">
      <h4>{{ food.name }}</h4>
    </food-item>
  </div>

  <footer>
    <food-item>
      <h4>Footer</h4>
    </food-item>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      foods: [
        { name: 'Apple', url: 'img_apple.svg' },
        { name: 'Pizza', url: 'img_pizza.svg' },
        { name: 'Rice', url: 'img_rice.svg' },
        { name: 'Fish', url: 'img_fish.svg' },
        { name: 'Cake', url: 'img_cake.svg' }
      ]
    };
  },
  methods: {
    getImageUrl(imageName) {
     return new URL(`./assets/${imageName}`, import.meta.url).href;
    }
  }
};
</script>
<style>
#wrapper {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
  }
  #wrapper > div {
    background-color: lightgreen;
  }
  footer > div {
    background-color: lightpink;
  }
  #wrapper img {
    display: block; 
    margin: 20% auto 0; 
    width: 60%;
  }
  h3, h4 {
    text-align: center;
  }
</style>