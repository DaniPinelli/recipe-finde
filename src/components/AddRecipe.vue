<template>
    <div id="add-container" class="container-add d-flex justify-content-center">
        <form @submit="addRecipe" >
            <label>Image</label>
            <input type="text" v-model="url" placeholder="Insert URL" ><br>
            <label>Name</label>
            <input type="text" v-model="title" placeholder="Your answer" ><br>
            <label>Recipe Type</label><br>
            <div class="form-check form-check-inline">
               <input v-model="type" class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio1" value="Salty">
               <label class="form-check-label" for="inlineRadio1">Salty</label>
            </div><br>
            <div class="form-check form-check-inline">
               <input v-model="type" class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio2" value="Sweet">
               <label class="form-check-label" for="inlineRadio2">Sweet</label>
            </div><br>
            
            <label>Ingredients</label><br>
            
            <input v-model="ingredients" type="checkbox" id="cbox1" value="Banana"> <label for="cbox1" >Banana</label>
            <input v-model="ingredients" type="checkbox" id="cbox2" value="Raspberry"> <label for="cbox2">Raspberry</label>
            <input v-model="ingredients" type="checkbox" id="cbox3" value="Sugar"> <label for="cbox3">Sugar</label><br>
            <input v-model="ingredients" type="checkbox" id="cbox4" value="Cheese"> <label for="cbox4">Cheese</label>
            <input v-model="ingredients" type="checkbox" id="cbox5" value="Milk"> <label for="cbox5">Milk</label>
            <input v-model="ingredients" type="checkbox" id="cbox6" value="Salt"> <label for="cbox6">Salt</label><br>
            <input v-model="ingredients" type="checkbox" id="cbox7" value="Potatoes"> <label for="cbox7">Potatoes</label>
            <input v-model="ingredients" type="checkbox" id="cbox8" value="Lentils"> <label for="cbox8">Lentils</label>
            <input v-model="ingredients" type="checkbox" id="cbox9" value="Macaroni"> <label for="cbox9">Macaroni</label><br>
            <input v-model="ingredients" type="checkbox" id="cbox10" value="Eggs"> <label for="cbox10">Eggs</label>
            <input v-model="ingredients" type="checkbox" id="cbox11" value="Peas"> <label for="cbox11">Peas</label>
            <input v-model="ingredients" type="checkbox" id="cbox12" value="Tomatoes"> <label for="cbox12">Tomatoes</label><br>

            <button type="submit" class="btn btn-dark">Submit</button>
            
        </form>
    </div>
</template>
<script>
//import {uuid} from 'uuid';

export default {
    name: 'AddRecipe',
    data(){
        return{
          title: "",
          ingredients: [],
          type:"",
          url: ""
        }
    },
    methods:{
        addRecipe(e){
          e.preventDefault();

          const newRecipe = {
              id: 20,//uuid(),
              title: this.title,
              ingredients: this.ingredients,
              type:this.type ,
              url: this.url 
          };

          this.title = "";
          this.ingredients= "";
          this.type = "";
          this.url = "";

          this.$emit('add-recipe', newRecipe);

        }
    }
}
</script>
<style scoped>

</style>