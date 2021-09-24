<template>

    <div id="finder-container" class="mt-3 background">
        <div>
        <div>
            <h1>Recipe Finder</h1>
            <input class="finder-placeholder mt-3" type="text" v-model="query" placeholder=" Add Ingredient" v-on:input="$emit('query-change', query.toLowerCase())"><br>
        </div>    
    
            <div class="form-check form-check-inline mt-3">
               <label class="form-check-label" for="inlineRadio1">Salty</label>
               <input v-model="typeFinder" class="form-check-input" type="radio" name="inlineRadioOptions" v-on:input="$emit('typeFinder', typeFinder)" id="inlineRadio1" value="Salty">
            </div>
            <div class="form-check form-check-inline  mt-3">
               <input v-model="typeFinder" class="form-check-input" type="radio" name="inlineRadioOptions" v-on:input="$emit('typeFinder', typeFinder)" id="inlineRadio2" value="Sweet">
               <label class="form-check-label" for="inlineRadio2">Sweet</label>
            </div>
        <!--  <div class="tags-containerl mt-3" >
                <div class="tags">
                    <p>Tags</p>
                </div>
                   <div class="each-tag d-flex" >
                     <div class="tag">
                        <p></p>
                        <button></button>
                    </div>
                
               </div>

             </div> -->
       </div>      
    </div>   
</template>
<script>


export default  {
   name: 'Finder',
     data() {
       return{
           query:"",
            },
            {
           typeFinder:"",
            }
        }
    
}
</script>
<style scoped>
#finder-container{
    width: 510px;
    height: 16rem;

}

.tag{
    display: flex;
}

</style>