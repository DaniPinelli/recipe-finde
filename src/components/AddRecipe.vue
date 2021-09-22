<template class="d-flex justify-content-center">
    <div id="add-container" class="container-add d-flex justify-content-center">
        <div>
        <div class="title-add mt-3" >
            <h3 class="title-create ml-3 pt-3 pb-3" >Create new recipe</h3>
        </div>
        <form @submit="addRecipe" >

            <div class="img-add mt-2">
                <label class="img-label ml-3 pt-2 " >Image</label><br>
            <input class="img-imput ml-3 pt-1 mb-4" type="text" v-model="url" placeholder="Insert URL" >
            </div>
            
            <div class="name-add mt-2">
            <label class="name-label ml-3 pt-2" >Name</label>
            <input class="name-imput ml-3 pt-1 mb-4" type="text" v-model="title" placeholder="Your answer" >
            </div>

            <div class="ingredients-add mt-2" >
                <label class="ingredients-label ml-3 pt-3 ">Ingredients</label>
            
            <div class="ingredients-group ml-2 pt-1 d-flex" >
            <div class="ingredients-1 ml-2">
              <div><input class="input-banana" v-model="ingredients" type="checkbox" id="cbox1" value="Banana"> <label for="cbox1" >Banana</label></div>
              <div><input class="input-raspberry" v-model="ingredients" type="checkbox" id="cbox2" value="Raspberry"> <label for="cbox2">Raspberry</label></div>
              <div><input class="input-sugar" v-model="ingredients" type="checkbox" id="cbox3" value="Sugar"> <label for="cbox3">Sugar</label></div>
            </div>
            <div class="ingredients-2">
              <div><input class="input-cheese" v-model="ingredients" type="checkbox" id="cbox4" value="Cheese"> <label for="cbox4">Cheese</label></div>
              <div><input class="input-milk" v-model="ingredients" type="checkbox" id="cbox5" value="Milk"> <label for="cbox5">Milk</label></div>
              <div><input class="input-salt" v-model="ingredients" type="checkbox" id="cbox6" value="Salt"> <label for="cbox6">Salt</label></div>
             </div>
            <div class="ingredients-3">
              <div><input class="input-potatoes" v-model="ingredients" type="checkbox" id="cbox7" value="Potatoes"> <label for="cbox7">Potatoes</label></div>
              <div><input class="input-lentils" v-model="ingredients" type="checkbox" id="cbox8" value="Lentils"> <label for="cbox8">Lentils</label></div>
              <div><input class="input-macaroni" v-model="ingredients" type="checkbox" id="cbox9" value="Macaroni"> <label for="cbox9">Macaroni</label></div>
            </div>
            <div class="ingredients-4 mb-3">
              <div><input class="input-eggs" v-model="ingredients" type="checkbox" id="cbox10" value="Eggs"> <label for="cbox10">Eggs</label></div>
              <div><input class="input-peas" v-model="ingredients" type="checkbox" id="cbox11" value="Peas"> <label for="cbox11">Peas</label></div>
              <div><input class="input-flour" v-model="ingredients" type="checkbox" id="cbox12" value="Flour"> <label for="cbox12">Flour</label></div>
              </div>
            </div>
            </div>
           
           <div class="recipe-add mt-2" >
               <label class="recipe-type ml-3" >Recipe Type</label><br>
            <div class="form-check form-check-inline">
               <input v-model="type" class="form-check-input ml-3" type="radio" name="inlineRadioOptions" id="inlineRadio1" value="Salty">
               <label class="form-check-label" for="inlineRadio1">Salty</label>
            </div><br>
            <div class="form-check form-check-inline ml-3 pb-3">
               <input v-model="type" class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio2" value="Sweet">
               <label class="form-check-label " for="inlineRadio2">Sweet</label>
            </div>
           </div>
            
            <button type="submit" class="btn btn-red mt-2 pl-4 pr-4">Submit</button>
            
        </form>
        </div>
    </div>
</template>
<script>
import {uuid} from 'vue-uuid';

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
              id: uuid.v4(),
              title: this.title,
              ingredients: this.ingredients,
              type:this.type ,
              url: this.url 
          };

          this.title ="";
          this.ingredients= [];
          this.type ="";
          this.url ="";

          this.$emit('add-recipe', newRecipe);

        }
    }
}
</script>
<style scoped>
.container-add{
    background-color:#FCD2D1;
    height:624px;
    width: 32rem;
    margin-left: auto;
    margin-right: auto;
    border-top:6px solid black;
}

.title-add{
    background-color:#fff;
    width: 28rem;
    border-radius: 5px;
    border-top:5px solid #FF5C58;
}

.img-add{
    background-color:#fff;
    width: 28rem;
    border-radius: 5px;
}

.img-imput{
  outline: 0;
  border-width: 0 0 2px;
  border-color: #D3D3D3;
  width:14rem;
}

.name-add{
    background-color:#fff;
    width: 28rem;
    border-radius: 5px;
}

.name-label{
    background-color:#fff;
    width: 27rem;
    border-radius: 5px;
}

.name-imput{
  outline: 0;
  border-width: 0 0 2px;
  border-color: #D3D3D3;
  width:14rem;
}

.ingredients-add{
    background-color:#fff;
    width: 28rem;
    border-radius: 5px;
}

.ingredients-label{
    background-color:#fff;
    width: 27rem;
    border-radius: 5px;
}

.ingredients-add{
background-color:#fff;
}

.ingredients-1{
    width: 7rem
}
.ingredients-2{
    width: 6rem
}
.ingredients-3{
    width: 7rem
}
.ingredients-4{
    width: 7rem
}

.recipe-add{
background-color: #fff;
    width: 28rem;
    border-radius: 5px;
}

.btn-red{
background-color: #FF5C58;
color:#fff;
font-size:small;
}



</style>