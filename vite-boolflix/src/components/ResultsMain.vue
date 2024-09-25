<script>

export default {
props:{
medias: Array //Array che sarà costruito in App.vue

},methods:{
voteInFive(vote){
    return Math.ceil(vote / 2) //Arrotondo il voto
}
},
  data() { 
        return {
            
        }
    }, 
}
</script>

<template>

<div class="container mt-4" v-for="media in medias" :key="media.id">
    <div class="card" style="width: 18rem;">
        <img class="card-img-top d-block" :src="'https://image.tmdb.org/t/p/w342/' + media.poster_path" alt="Card image cap">
 <p>Titolo originale: <h4 class="text-success d-inline"> {{ media.original_title }}</h4></p>
 <p>Traduzione titolo:<h5>{{ media.title }}</h5></p>
 <p>Lingua originale:<h5>{{ media.original_language }}</h5></p>
 <p>Valutazione:<h6>{{ voteInFive(media.vote_average) }}</h6></p>
  
 </div>
</div>
  
 
</template>

<style lang="scss">
@import "bootstrap/scss/bootstrap"


</style>
