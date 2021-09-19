<template>
  <div>
    <div id="header" ></div>
    <div id="main-container" >
      <h1  class="text-center" >Recipes</h1>
      <Recipes v-bind:recipesList="copyRecipes"/>
    </div>
  </div>
</template>

<script>
import Recipes from './components/Recipes.vue'


export default {
  name: 'App',
  components: {
   Recipes
  }, 
  data () {
    return{
      recipes:[
        {
          id:0,
          title: "Banana's Bread",
          ingredients: ["Bananas", "Milk", "Sugar", "Flour"],
          type:"Sweet",
          url: "../assets/images/banannaBread.jpg"
        },
        {
          id:1,
          title: "Lentil Stew",
          ingredients: ["Lentils", "Potatoes", "Salt", "Sauce"],
          type:"Salty",
          url: "../assets/images/lentilStew.jpg"
        },
        {
          id:2,
          title: "Mac and Cheese",
          ingredients: ["Macaroni", "Cheese", "Salt", "Milk"],
          type:"Salty",
          url: "../assets/images/macAndCheese.jpg"
        },
        {
          id:3,
          title: "Raspberry Muffins",
          ingredients: ["Raspberry", "Milk", "Sugar", "Flour"],
          type:"Sweet",
          url: "../assets/images/raspberryMuffins.jpg"
        },
        {
          id:4,
          title: "Pea Omelette",
          ingredients: ["Peas", "Eggs", "Cheese", "Salt"],
          type:"Salty",
          url: "../assets/images/peaOmelette.jpg"
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
