<template>
  <div id="app">
     
  </div>
</template>

<script>
import axios from 'axios'


export default {
  name: 'App',
  components: {
    
  },
  data(){
    return{
      filteredMovies:[]
    }
  },
  methods:{
    getMovies(name){
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=e5b44d73cf6acb74493cea658f17750e&query=${name}&language=it`).then((list)=>{
          this.filteredMovies=list.data.results
      })
    }
  }
}
</script>

<style lang="scss">

</style>
