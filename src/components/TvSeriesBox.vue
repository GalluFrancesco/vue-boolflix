<template>
    <div class="series-box">
        <card-movie v-for="serie in series"
        :key="serie.id" 
        :movie="serie"/>
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