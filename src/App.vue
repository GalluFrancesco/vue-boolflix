<template>
  <div id="app">
     <header-box @search="getMovies"/>
     <main-box :movies="filteredMovies"/>
  </div>
</template>

<script>
import axios from 'axios'
import HeaderBox from './components/HeaderBox.vue'
import MainBox from './components/MainBox.vue'


export default {
  name: 'App',
  components: {
    HeaderBox,
    MainBox,

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
