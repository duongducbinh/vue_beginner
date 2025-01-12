<template> 
  <h1>Food</h1>
  <p>The user can now change the favorite status of the food items with the use of a new data property initialized by the 'is-favorite' prop value.</p>
  <div class="wrapper">
    <food-item 
      v-for="food in foods"
      :key="food.name"
      :food-name="food.name"
      :food-desc="food.desc"
      :is-favorite="food.isFavorite"
      @toggle-favorite="ToggleFavorite"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      foods: [
        { name: 'Pizza', desc: 'A delicious food', isFavorite: true },
        { name: 'Burger', desc: 'A tasty food', isFavorite: false },
        { name: 'Pasta', desc: 'A yummy food', isFavorite: false }
      ]
    }
  },

  methods: {
    ToggleFavorite(foodName){
      const food = this.foods.find(f => f.name === foodName);
      food.isFavorite = !food.isFavorite;
    }
  }
}


</script>
<style>
#wrapper {
    display: flex;
    flex-wrap: wrap;
  }
  #wrapper > div {
    border: dashed black 1px;
    flex-basis: 120px;
    margin: 10px;
    padding: 10px;
    background-color: lightgreen;
  }
</style>