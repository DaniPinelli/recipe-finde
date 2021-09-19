<template>
<div>
    <div class="container-cards d-flex justify-content-center" >
      <div class="card">
         <img class="card-img-top image-recipe" src= {{recipe.url}} v-bind:alt="pic">
         <div class="card-title" ><h5> {{recipe.title}} </h5> </div>
         <div class="mb-0"><p><strong>Type:</strong> {{recipe.type}} </p> </div>
         <div class="card-text" > <p><strong>Ingredients:</strong> {{recipe.ingredients[0]}}, {{recipe.ingredients[1]}}, {{recipe.ingredients[2]}}, {{recipe.ingredients[3]}}.</p></div>
      </div>
    </div>
</div>
    
</template>

<script>


export default {
   name: 'RecipeItem',
   props: ['recipe']
}
</script>

<style scoped>

.card{
border-color: #fff;
}

.image-recipe{
    height: 160px;
    width: auto;
    border-radius: 5px #fff solid;
}

</style>
