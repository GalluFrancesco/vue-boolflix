<template>
  <div id="app">
     <header-box @search="getMovies"/>
     <main-box :movies="filteredMovies" :series="filterdTvSeries"/>
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
      filteredMovies:[],
      filterdTvSeries:[],
      api_key: 'e5b44d73cf6acb74493cea658f17750e'
    }
  },
  methods:{
    getMovies(query){
      this.getApi(query,'movie')
      this.getApi(query,'tv')
    },

    getApi(query, type){

    const params={
      query:query,
      api_key:this.api_key,
      language:'it'
    }
      if(type==='movie'){
          axios.get(`https://api.themoviedb.org/3/search/${type}`, {params}).then((list)=>{
          this.filteredMovies=list.data.results
          })
      }
      if(type==='tv'){
          axios.get(`https://api.themoviedb.org/3/search/${type}`, {params}).then((list)=>{
          this.filterdTvSeries=list.data.results
          })
      }

      

    }
  }
}
</script>

<style lang="scss">
@import './style/main.scss';
  #app{
    background-color: #434343;
    width: 100%;
    min-height: 100vh;
  }
</style>
