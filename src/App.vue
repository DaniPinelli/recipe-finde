<template>
  <div>
    <div id="header" ></div>
    <div id="main-container" >
      <h2>Recipes</h2>
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
          title: "Banana's bread",
          ingredients: ["Bananas", "milk", "sugar", "flour"],
          type:"sweet",
          url: ""
        },
        {
          id:1,
          title: "Banana's bread",
          ingredients: ["Bananas", "milk", "sugar", "flour"],
          type:"sweet",
          url: ""
        },
        {
          id:2,
          title: "Banana's bread",
          ingredients: ["Bananas", "milk", "sugar", "flour"],
          type:"sweet",
          url: ""
        },
        {
          id:3,
          title: "Banana's bread",
          ingredients: ["Bananas", "milk", "sugar", "flour"],
          type:"sweet",
          url: ""
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
