<template>
    <div id="finder-container" class="container-finder" >
        <h1>Recipe Finder</h1>
        <input type="text" v-model="query" placeholder=" Add Ingredient" v-on:input="$emit('query-change', query)"><br>
            <div class="form-check form-check-inline">
               <label class="form-check-label" for="inlineRadio1">Salty</label>
               <input v-model="type" class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio1" value="Salty">
            </div>
            <div class="form-check form-check-inline">
               <input v-model="type" class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio2" value="Sweet">
               <label class="form-check-label" for="inlineRadio2">Sweet</label>
            </div>

            <div class="tags-containerl" >
                <div class="tags">
                    <p>Tags</p>
                </div>
                <div class="each-tag d-flex" >
                    <div class="tag">
                      <p></p>
                      <button></button>
                    </div>
                
                </div>

            </div>
            
    </div>
</template>
<script>


export default  {
   name: 'Finder',
   data(){
       return{
           query:""
       }
   }
}
</script>
<style scoped>
#finder-container{
    width: 280px;
    height: 3rem;
}

.tag{
    display: flex;
}
</style>