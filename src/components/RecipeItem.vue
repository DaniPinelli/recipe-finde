<template>
<div  class="hide mt-3">
    <div class="container-cards" >
      <div class="card each-card">
         <img class="card-img-top image-recipe" :src="recipe.url" :alt="recipe.title">
         <div class="card-title mt-2" ><h5> {{recipe.title}} </h5> </div>
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
height: 300px;
width: 290px;
border-radius: 5px #fff solid;
}

.each-card{
  width: 20rem;
}

.hide{
  /* display:none;*/
}


</style>
