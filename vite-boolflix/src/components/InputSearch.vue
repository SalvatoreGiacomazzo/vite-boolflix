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
<div class="container mt-4">
 <div class="input-group">
  <input v-model="resultsQuery" type="search" class="form-control rounded" placeholder="Search a movie..."  />
  <button @click="searchRequest" type="button" class="btn btn-outline-primary" data-mdb-ripple-init>search</button>
 </div>
</div>
</template>

<style lang="scss">



</style>