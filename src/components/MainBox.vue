<template>
    <main>
        <!-- test per verificare il funzionamento -->
        <movies-box :movies="movies" />
        <tv-series-box :series="series" />
    </main>
</template>

<script>
import MoviesBox from './MoviesBox.vue'
import TvSeriesBox from './TvSeriesBox.vue'
export default {
    components: {
        MoviesBox,
        TvSeriesBox
    },
    props:{
        movies:Array,
        series:Array
    }
}
</script>

<style lang="scss" scoped>


</style>