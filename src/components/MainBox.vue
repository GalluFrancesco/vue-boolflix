<template>
    <main>
        <!-- test per verificare il funzionamento -->
        <movies-box :movies="movies" />

    </main>
</template>

<script>
import MoviesBox from '../components/MoviesBox.vue'
export default {
    components: {
        MoviesBox

    },
    props:{
        movies:Array
    }
}
</script>

<style lang="scss" scoped>


</style>