<script>


export default {
    data() {
        return{
            vote: [],
            emptyStar: [],
        }
    },
    props: {
        film:{
            type:Array,
            required:true
        },
        series:{
            type:Array,
            required:true
        }
    },
    methods: {
        votefix() {
            let intVote = parseInt(Math.ceil(this.film.vote_average) / 2, 10);
            for (let index = 0; index < intVote; index++) {
                this.vote.push(index);
            };
            for (let index = intVote; index < 5; index++) {
                this.emptyStar.push(index);
            };
            
        }
    },
    created(){
        this.votefix();
    },
}
</script>

<template>
    <div id="star">
    <!-- Add the style and icon you want using the String format -->
    <font-awesome-icon icon="fa-solid fa-star" />
    </div>
    <article v-for="(film, index) in film" :key="index" :film="film">
        <h1>{{ film.original }} </h1>
        <h2> {{ film.original_title }} </h2>
        <ul>
            <li v-for="(vote, index) in vote" :key="index"  class="yellow">
                <font-awesome-icon icon="fa-solid fa-star" />
            </li>
            <li v-for="(emptyStar, index) in emptyStar" :key="index" class="gray">
                <font-awesome-icon icon="fa-solid fa-star" />
            </li>
        </ul>  
        <img  v-bind:src="`https://image.tmdb.org/t/p/w342/${ film.backdrop_path }`"  alt="img">
        <span class="lang-icon" :class="`lang-icon-${ film.original_language }`"></span>
    </article>
    <article v-for="(series, index) in series" :key="index" :series="series">
        <h1> {{ series.original_name }} </h1>
        <h2> {{ series.name }}</h2>
        <ul>
            <li v-for="(vote, index) in vote" :key="index" id="app" class="yellow">
                <font-awesome-icon icon="fa-solid fa-star" />
            </li>
            <li v-for="(emptyStar, index) in emptyStar" :key="index" id="app" class="gray">
                <font-awesome-icon icon="fa-solid fa-star" />
            </li>
        </ul>    
        <img  v-bind:src="`https://image.tmdb.org/t/p/w342/${ series.backdrop_path }`"  alt="img">
        <span class="lang-icon" :class="`lang-icon-${ series.original_language}`"></span>
    </article>
</template>

<style lang="scss" scoped>
.lang-icon {
            background-image: url(../../node_modules/@textabledev/langs-flags-list/lang-flags.png);
        }

.lang-icon {
    display: inline-block;
    width: 25px;
    height: 15px;
    }
</style>