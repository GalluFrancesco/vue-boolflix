<template>
    <div class="movies-box">
        <card-movie v-for="movie in movies"
        :key="movie.id" 
        :movie="movie"/>
    </div>
</template>

<script>
import CardMovie from '../components/CardMovie.vue'
export default {
    components: {
        CardMovie

    },
    props:{
        movies:Array
    }
    
}
</script>

<style lang="scss" scoped>
@import '../style/main.scss';

</style>