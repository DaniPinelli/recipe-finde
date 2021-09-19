<template>
    <div>
        <div v-bind:key="recipe.id" v-for="recipe in recipesList" >
        <div> {{recipe.title}}</div>
        </div>
    </div>
</template>

<script>

export default {
    name: 'Recipes', 
    props: ['recipesList']
}
</script>
