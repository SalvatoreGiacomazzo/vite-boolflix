<script>


export default {
  data() {
    return {
      resultsQuery: '', 
    };
  },
  methods: {
    searchRequest() {
      //Custom event per comunicare con il parent
      this.$emit('search', this.resultsQuery);
    },
  },
};

</script>

<template>
<header class="bg-dark d-flex justify-content-between align-items-center">
  <div class="container">
    <h2 class="text-danger">BOOLFLIX</h2>
  <div class="input-group w-50">
    <input v-model="resultsQuery" v-on:keyup.enter="searchRequest"  type="search" class="form-control rounded" placeholder="Search a movie..."  />
    <button @click="searchRequest" type="button" class="btn btn-outline-primary" data-mdb-ripple-init>search</button>
  </div>
  </div>
</header>
</template>

<style lang="scss">
header{
  height: 100px;

}

</style>