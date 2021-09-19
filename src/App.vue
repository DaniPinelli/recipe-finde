<template>
  <div>
    <div id="header" ></div>
    <div id="main-container" >
      <h1 class="text-center" >Add Recipe</h1>
      <AddRecipe/>
      <h2  class="text-center" >Recipes List</h2>
      <Recipes v-bind:recipesList="copyRecipes"/>
    </div>
  </div>
</template>

<script>
import Recipes from './components/Recipes.vue'
import AddRecipe from './components/AddRecipe.vue'

export default {
  name: 'App',
  components: {
   AddRecipe, Recipes
  }, 
  data () {
    return{
      recipes:[
        {
          id:0,
          title: "Banana's Bread",
          ingredients: ["Bananas", "Milk", "Sugar", "Flour"],
          type:"Sweet",
          url: "../public/images/banannaBread.jpg"
        },
        {
          id:1,
          title: "Lentil Stew",
          ingredients: ["Lentils", "Potatoes", "Salt", "Sauce"],
          type:"Salty",
          url: "../public/images/lentilStew.jpg"
        },
        {
          id:2,
          title: "Mac and Cheese",
          ingredients: ["Macaroni", "Cheese", "Salt", "Milk"],
          type:"Salty",
          url: "../public/images/macAndCheese.jpg"
        },
        {
          id:3,
          title: "Raspberry Muffins",
          ingredients: ["Raspberry", "Milk", "Sugar", "Flour"],
          type:"Sweet",
          url: "../public/images/raspberryMuffins.jpg"
        },
        {
          id:4,
          title: "Pea Omelette",
          ingredients: ["Peas", "Eggs", "Cheese", "Salt"],
          type:"Salty",
          url: "../public/images/peaOmelette.jpg"
        }
      ],
      copyRecipes: []
    }
  }, 
  created () {
    this.copyRecipes = [...this.recipes];
  }
}
</script>

<style>

</style>
