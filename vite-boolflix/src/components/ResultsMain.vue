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
    <div class="card movie-card" style="width: 18rem;">
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
@import "bootstrap/scss/bootstrap";

.movie-card .card-body{
    opacity:0;
    position: absolute;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  transition: opacity 0.2s ease-in-out;
  background-color: white;

}

.movie-card:hover .card-body {
  opacity: 1;
}


.movie-card{
    overflow:hidden;
    position: relative;
}

.movie-card:hover img{
opacity: 0;
transition: opacity 0.2s ease-in-out
}
</style>
