<script>

export default {
props:{
movies: Array //Array che sarà costruito in App.vue

},methods:{
voteInFive(vote){
    return Math.round(vote / 2) //Arrotondo il voto
}
},
  data() { 
        return {
            
        }
    }, 
}
</script>

<template>
<div class="container mt-4" v-for="movie in movies" :key="movie.id">
 <h1 class="text-success"> {{ movie.title }}</h1>
 <h2>{{ movie.original_title }}</h2>
 <h3>{{ movie.original_language }}</h3>
 <h4>{{ voteInFive(movie.vote_average) }}</h4>
 <img class="d-block w-50":src="'https://image.tmdb.org/t/p/w500/' + movie.poster_path" alt="#">

</div>
  
 
</template>

<style lang="scss">
@import "bootstrap/scss/bootstrap"


</style>
