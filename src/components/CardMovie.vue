<template>
    <div class="card">
        <div class="box-img">
            <img :src="'https://image.tmdb.org/t/p/original/' + movie.poster_path"/>
        </div>
        <p><b>Titolo:</b> {{movie.title}}</p>
        <p><b>Titolo originale:</b> {{movie.original_title}}</p>
        <p class="box-language"><b>Lingua:</b>
            <img class="flag" :src="`/flags/${movie.original_language}.png`" alt="">
        </p>
        <p><b>Voto:</b> {{movie.vote_average}}</p>
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
        height: 450px;
        margin: 20px 20px;
        padding: 40px 10px;
        position: relative;
        
        .box-img{
            height: 450px;
            width: 298px;
            position: absolute;
            top: 0;
            left: 0;

            img{
                width: 100%;
                object-fit: cover;
            }

            &:hover img{
                display: none;
            }
        }
        p{
            font-family: Arial, Helvetica, sans-serif;
            line-height: 35px;
            font-size: 20px;

            
        }
        .box-language{
            display: flex;
            align-items: center;
        
            .flag{
                height: 25px ;
            }
        }
        
    }
</style>