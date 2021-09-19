<template>
    <div id="finder-container" class="container-finder" >
        <h1>Recipe Finder</h1>
        <input type="text" v-model="query" placeholder="Search" v-on:input="$emit('query-change', query)">
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
</style>