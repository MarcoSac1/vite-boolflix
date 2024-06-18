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
        voteFix() {
            let intVote = (Math.ceil(this.film.vote_average )/ 2, 5);
            console.log(intVote);
            for (let index = 0; index < intVote; index++) {
                this.vote.push(index);
            };
            console.log(this.vote);
            for (let index = intVote; index < 5; index++) {
                this.emptyStar.push(index);
            };
            console.log(this.emptyStar);
            
        }
    },
    created(){
        this.voteFix();
    },
}
</script>

<template>
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
            <li v-for="(vote, index) in vote" :key="index"  class="yellow">
                <font-awesome-icon icon="fa-solid fa-star" />
            </li>
            <li v-for="(emptyStar, index) in emptyStar" :key="index"  class="gray">
                <font-awesome-icon icon="fa-solid fa-star" />
            </li>
        </ul>    
        <img  v-bind:src="`https://image.tmdb.org/t/p/w342/${ series.backdrop_path }`"  alt="img">
        <span class="lang-icon" :class="`lang-icon-${ series.original_language}`"></span>
    </article>
</template>

<style lang="scss" scoped>
    @use '../styles/flag-icon.scss' as *;

    
    .lang-icon {
        background-image: url(../../node_modules/@textabledev/langs-flags-list/lang-flags.png);
    }
    ul{
        list-style-type: none;
        display: flex;
        padding-left: 0rem;
        li{
            margin: .2rem;
        }
    }
    .yellow{
        color: rgb(100, 206, 30);
    }
    .gray{
        color: gray;
    }
</style>