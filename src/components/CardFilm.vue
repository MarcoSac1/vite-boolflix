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
            console.log(this.film);
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
    <div class="container-fluid">
        <section class="row">
            <div class="card m-2 p-0 bg-secondary text-light" style="width: 18rem;" v-for="(film, index) in film" :key="index" :film="film">
                <img class="col-12" v-bind:src="`https://image.tmdb.org/t/p/w342/${ film.backdrop_path }`"  alt="img">
                <div class="card-body">
                    <h2>{{ film.original }} </h2>
                    <h4  class=""> {{ film.original_title }} </h4>
                    <p class="">{{ film.vote_average }}</p>
                    <ul>
                        <li v-for="(vote, index) in vote" :key="index"  class="yellow">
                            <font-awesome-icon icon="fa-solid fa-star" />
                        </li>
                        <li v-for="(emptyStar, index) in emptyStar" :key="index" class="gray">
                            <font-awesome-icon icon="fa-solid fa-star" />
                        </li>
                    </ul> 
                    <span class="lang-icon" :class="`lang-icon-${ film.original_language }`"></span> 
                </div>
            </div>
        </section>
    </div>
    <div class="container-fluid">
        <section class="row">
            <div class="card m-2 p-0 bg-secondary text-light" style="width: 18rem;" v-for="(series, index) in series" :key="index" :series="series">
                <img class="col-12" v-bind:src="`https://image.tmdb.org/t/p/w342/${ series.backdrop_path }`"  alt="img">
                <div class="card-body ">
                    <h2>{{ series.name }} </h2>
                    <h4  class=""> {{ series.name }} </h4>
                    <p >{{ film.vote_average }}</p>
                    <ul>
                        <li v-for="(vote, index) in vote" :key="index"  class="yellow">
                            <font-awesome-icon icon="fa-solid fa-star" />
                        </li>
                        <li v-for="(emptyStar, index) in emptyStar" :key="index" class="gray">
                            <font-awesome-icon icon="fa-solid fa-star" />
                        </li>
                    </ul> 
                    <span class="lang-icon" :class="`lang-icon-${ series.original_language }`"></span> 
                </div>
            </div>
        </section>
    </div>
</template>

<style lang="scss" scoped>
    @use '../styles/flag-icon.scss' as *;

    img{
        width: 100%;
        padding: .2rem;
    }
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