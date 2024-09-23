<script>

export default {
props:{
movies: Array //Array che sarà costruito in App.vue
},
  data() {
        return {
  
        }
    }
}
</script>

<template>
<div class="container mt-4" v-for="movie in movies" :key="movie.id">
 <h1 class="text-success"> {{ movie.title }}</h1>
 <h2> original title</h2>
 <h3>lang</h3>
 <h4>rate</h4>

</div>
  
 
</template>

<style lang="scss">
@import "bootstrap/scss/bootstrap"


</style>
