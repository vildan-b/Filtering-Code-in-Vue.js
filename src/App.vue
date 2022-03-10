<template>
  <div class="container">
    <div class="row">
      <div class="col-md-6 col-md-offset-3">
        <h3>Filtering Code in Vue.js</h3>
        <p> {{ message | toUpperCase }} </p>
        <hr> <br>
        <input type="text" v-model="searchText">
        <hr> <br>
        <ul>
        <li v-for="city in filtered"> {{ city }}</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
data(){
  return {
    message : "Filtering Code in Vue.js",
    searchText : "",
    cities : ["Berlin", "Hamburg","Munich","Frankfurt","Bremen","Düsseldorf",
    "Stuttgart","Leipzig","Dortmund","Essen","Hannover","Nuremberg","Duisburg","Kassel"]
  }
},
filters:{
  toUpperCase(value){
return value.toUpperCase();
  }
},
computed:{
  filtered(){
    return this.cities.filter((element) =>{
      return element.match(this.searchText);
    })
  }

}

}
</script>

<style>

</style>
