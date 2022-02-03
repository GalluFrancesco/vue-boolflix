<template>
    <main>
        <!-- test per verificare il funzionamento -->
        <card-movie v-for="movie in movies"
        :key="movie.id" 
        :movie="movie"/>

    </main>
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

main{  
    display: flex;
    flex-wrap: wrap;
    width: 1360px;
    margin: 0 auto;
    padding: 40px 0;
}

</style>