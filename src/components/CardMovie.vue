<template>
    <div class="card">
        <div><b>Titolo:</b> {{movie.title}}</div>
        <div><b>Titolo originale:</b> {{movie.original_title}}</div>
        <div><b>Lingua:</b> {{movie.original_language}}</div>
        <div><b>Voto:</b> {{movie.vote_average}}</div>
    </div>
</template>

<script>
export default {
    props:{
        movie: Object
    }
}
</script>

<style lang="scss" scoped>
    .card{
        background-color: black;
        border:white solid 1px;
        color: white;
        width: 300px;
        height: 500px;
        margin: 20px 20px;
        padding: 40px 10px;
        font-size: 25px;
    }
</style>