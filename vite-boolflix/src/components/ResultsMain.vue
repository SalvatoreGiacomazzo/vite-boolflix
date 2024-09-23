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
 <p>Titolo originale: <h4 class="text-success d-inline"> {{ movie.original_title }}</h4></p>
 <p>Traduzione titolo:<h5>{{ movie.title }}</h5></p>
 <p>Lingua originale:<h5>{{ movie.original_language }}</h5></p>
 <p>Valutazione:<h6>{{ voteInFive(movie.vote_average) }}</h6></p>
 <img class="d-block":src="'https://image.tmdb.org/t/p/w342/' + movie.poster_path" alt="#">

</div>
  
 
</template>

<style lang="scss">
@import "bootstrap/scss/bootstrap"


</style>
