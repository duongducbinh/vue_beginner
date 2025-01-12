<template>
    <div>
        <h2>{{ foodName }}
            <img src="@/assets/img_quality.svg" v-show="isFavorite" alt="">
        </h2>
        <p>{{ foodDesc }}</p>
        <button v-on:click="ToggleFavorite">
            Favorite
        </button>
    </div>
</template>

<script>
export default {
    props: {
        foodName: String,
        foodDesc: String,
        isFavorite: Boolean 
    },


    methods: {
        ToggleFavorite(){
            this.$emit('toggle-favorite', this.foodName);
        }
    }
}
</script>

<style>
img {
    height: 1.5em;
    float: right;
  }
</style>