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
movies:[] //Array che verrà riempito con chiamata API
        }
    },
    methods:{
      searchRequest(query){
       const apiKey = "ae84bb1fd70b17b6b6a489a195aa80cf"           //Key che ho ottenuto con la registrazione
       const apiUrl =`https://api.themoviedb.org/3/search/movie?api_key=${apiKey}&query=${query}`

        //chiamata con Axios
        axios.get(apiUrl).then((response) => {
          this.movies = response.data.results
        }).catch((error) => {
         console.log('Errore')
        }) 
      }
    }
}






</script>

<template>
<InputSearch @search="searchRequest"/>

<ResultsMain :movies="movies"/>




</template>

<style lang ="scss" scoped>

@import "bootstrap/scss/bootstrap"


</style>
