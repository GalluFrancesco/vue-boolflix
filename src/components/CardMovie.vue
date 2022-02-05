<template>
    <div class="card">
        <div class="box-img">
            <img :src="'https://image.tmdb.org/t/p/original/' + movie.poster_path"/>
        </div>
        <div class="txt"><b>Titolo:</b> {{movie.title}}</div>
        <div class="txt"><b>Titolo originale:</b> {{movie.original_title}}</div>
        <div class="box-language txt"><b>Lingua:</b>
            <img 
            v-if="languages.includes(movie.original_language)"
            class="flag" 
            :src="`/flags/${movie.original_language}.png`"/>
            <div v-else>{{ movie.original_language }}</div>
        </div>
        <div class="txt"><b>Voto: </b>
            <span v-for="n in 5" :key="n">
                <i v-if="ratingToStars(n,movie.vote_average)" class="fas fa-star yellow"></i>
                <i v-else class="far fa-star"></i>
            </span>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
        languages: ["en", "it", "ja", "fr", "es", "zh", "de"],
        };
    },
    props:{
        movie: Object
    },
    methods:{
        ratingToStars(n, vote){
            //farò un v-for che ciclerà n volte(5)
            //all'interno metterò un v-if che utilizzerà questa funzione
            //quindi se sarà true stamperà una stella piena
            //v-else stella vuota
            return n <= Math.round(vote / 2);
        }
        
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
        .txt{
            font-family: Arial, Helvetica, sans-serif;
            line-height: 35px;
            font-size: 20px;

            
        }
        .box-language{
            display: flex;
            align-items: center;
        
            .flag{
                height: 25px ;
                margin-left: 5px;
            }
        }

        .yellow{
            color: yellow;
        }
        
    }
</style>