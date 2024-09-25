<script>
import ResultsMain from './components/ResultsMain.vue'
import InputSearch from './components/InputSearch.vue'
import axios from 'axios'

export default {
  components:{
    ResultsMain,
    InputSearch
  }, 
  data() {
        return {
medias:[] //Array che verrà riempito con chiamata API
        }
    },
    methods:{
      searchRequest(query){
       const apiKey = "ae84bb1fd70b17b6b6a489a195aa80cf"           //Key che ho ottenuto con la registrazione
       const apiMovies =`https://api.themoviedb.org/3/search/movie?api_key=${apiKey}&query=${query}`
       const apiTvSerie = `https://api.themoviedb.org/3/search/tv?api_key=${apiKey}&query=${query}`

        //chiamata con Axios
        axios.get(apiMovies).then((response) => {    
          const moviesFound = response.data.results
        
        return axios.get(apiTvSerie).then((response) =>   {
          const tvFound = response.data.results


          this.medias = [...moviesFound, ...tvFound];   
          console.log(this.medias);

        })
        
        
        
        
        
        
        }).catch((error) => {
         console.log('Errore')
        }) 
      }
    }
}






</script>

<template>
<InputSearch @search="searchRequest"/>

<ResultsMain :medias="medias"/>




</template>

<style lang ="scss" scoped>
@import "bootstrap/scss/bootstrap"


</style>

