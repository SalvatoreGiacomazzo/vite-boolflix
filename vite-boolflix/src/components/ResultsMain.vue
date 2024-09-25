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

<div class="container mt-4">
 <div class="row">
  <div class="col-md-3 mb-4" v-for="media in medias" :key="media.id">
    <div class="card" style="width: 18rem;">
        <img class="card-img-top d-block" :src="'https://image.tmdb.org/t/p/w342/' + media.poster_path" alt="Card image cap">
        <div class="card-body">
            <p>Titolo originale: <span class="text-success">{{ media.original_title }}</span></p>
            <p>Traduzione titolo: <span>{{ media.title }}</span></p>
            <p>Lingua originale: <span>{{ media.original_language }}</span></p>
            <p>Valutazione: <span>{{ voteInFive(media.vote_average) }}</span></p>
        </div>
    </div>
  </div>
 </div>
</div>
 
</template>

<style lang="scss">
@import "bootstrap/scss/bootstrap"


</style>
