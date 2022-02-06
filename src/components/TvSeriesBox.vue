<template>
    <div class="movies-box">
        <card-movie v-for="serie in series"
        :key="serie.id" 
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
        series:Array
    }
    
}
</script>

<style lang="scss" scoped>
@import '../style/main.scss';

</style>