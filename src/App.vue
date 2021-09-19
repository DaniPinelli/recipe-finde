<template>
  <div>
    <div id="header" ></div>
    <div id="main-container" >
      <h1 class="text-center" >Add Recipe</h1>
      <AddRecipe v-on:add-recipe="addRecipe"/>
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

  methods:{
  addRecipe(recipe){
    this.recipes.push(recipe);
    this.copyRecipes = [...this.recipes]
  }
  },
  data () {
    return{
      recipes:[
        {
          id:0,
          title: "Banana's Bread",
          ingredients: ["Bananas", "Milk", "Sugar", "Flour"],
          type:"Sweet",
          url: "../images/bananaBread.jpg"
        },
        {
          id:1,
          title: "Lentil Stew",
          ingredients: ["Lentils", "Potatoes", "Salt", "Sauce"],
          type:"Salty",
          url: "../images/lentilStew.jpg"
        },
        {
          id:2,
          title: "Mac and Cheese",
          ingredients: ["Macaroni", "Cheese", "Salt", "Milk"],
          type:"Salty",
          url: "../images/macAndCheese.jpg"
        },
        {
          id:3,
          title: "Raspberry Muffins",
          ingredients: ["Raspberry", "Milk", "Sugar", "Flour"],
          type:"Sweet",
          url: "../images/raspberryMuffins.jpg"
        },
        {
          id:4,
          title: "Pea Omelette",
          ingredients: ["Peas", "Eggs", "Cheese", "Salt"],
          type:"Salty",
          url: "../images/peaOmelette.jpg"
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
