<template>
<div >
    <div class="recipes-container mt-4 d-flex justify-content-center">
        <div v-bind:key="recipe.id" v-for="recipe in recipesList" >
            <RecipeItem v-bind:recipe="recipe" />
        </div>
    </div>
</div>
</template>

<script>
import RecipeItem from './RecipeItem.vue';

export default {
    name: 'Recipes', 
    props: ['recipesList'],
    components: {RecipeItem}
}
</script>
