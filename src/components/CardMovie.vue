<template>
    <main>
        <div>Titolo: {{movie.title}}</div>
        <div>Titolo originale: {{movie.original_title}}</div>
        <div>Lingua: {{movie.original_language}}</div>
        <div>Voto: {{movie.vote_average}}</div>
    </main>
</template>

<script>
export default {
    props:{
        movie: Object
    }
}
</script>

<style lang="scss" scoped>

</style>