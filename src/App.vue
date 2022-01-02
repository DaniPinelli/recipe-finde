<template>
  <div>
    <div id="main-container">
      <div>
        <AddRecipe v-on:add-recipe="addRecipe" />
      </div>

      <div class="finder-container d-flex justify-content-center">
        <Finder
          v-on:query-change="querySearch"
          v-on:selected-salty="SelectedSalty"
          v-on:selected-sweet="SelectedSweet"
        />
      </div>

      <div class="recipes-container mt-1">
        <h2 class="text-center">Results</h2>

        <Recipes v-bind:recipesList="copyRecipes" />
      </div>
    </div>
  </div>
</template>

<script>
import Recipes from "./components/Recipes.vue";
import AddRecipe from "./components/AddRecipe.vue";
import Finder from "./components/Finder.vue";

export default {
  name: "App",
  components: {
    AddRecipe,
    Finder,
    Recipes,
  },

  methods: {
    addRecipe(recipe) {
      this.recipes.push(recipe);
      this.copyRecipes = [...this.recipes];
    },

    querySearch(query) {
      if (query.trim() === "") {
        this.copyRecipes = [...this.recipes];
      } else if (this.recipe.type === "Salty") {
        [...this.recipes] = this.recipes.filter(
          (recipe) => recipe.type === "Salty"
        );
      } else if (this.recipe.type === "Sweet") {
        [...this.recipes] = this.recipes.filter(
          (recipe) => recipe.type === "Sweet"
        );
      } else {
        const temp = this.copyRecipes.filter((recipe) => {
          return recipe.title.toLowerCase().includes(query);
        });

        this.copyRecipes = [...temp];
      }
    },
  },
  data() {
    return {
      recipes: [
        {
          id: 0,
          title: "Banana's Bread",
          ingredients: ["Bananas", "Milk", "Sugar", "Flour"],
          type: "Sweet",
          url: require("@/assets/images/bananaBread.png"),
        },
        {
          id: 1,
          title: "Lentil Stew",
          ingredients: ["Lentils", "Potatoes", "Salt", "Sauce"],
          type: "Salty",
          url: require("@/assets/images/lentilStew.jpg"),
        },
        {
          id: 2,
          title: "Mac and Cheese",
          ingredients: ["Macaroni", "Cheese", "Salt", "Milk"],
          type: "Salty",
          url: require("@/assets/images/macAndCheese.jpg"),
        },
        {
          id: 3,
          title: "Raspberry Muffins",
          ingredients: ["Raspberry", "Milk", "Sugar", "Flour"],
          type: "Sweet",
          url: require("@/assets/images/raspberryMuffins.jpg"),
        },
        {
          id: 4,
          title: "Pea Omelette",
          ingredients: ["Peas", "Eggs", "Cheese", "Salt"],
          type: "Salty",
          url: require("@/assets/images/peaOmelette.jpg"),
        },
      ],
      copyRecipes: [],
    };
  },
  created() {
    this.copyRecipes = [...this.recipes];
  },
};
</script>

<style>
.finder-container {
  height: 290px;
}
</style>
