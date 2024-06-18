<script>
import AppSearch from './AppSearch.vue';
import axios from "axios";

export default {
    components:{
        AppSearch
    },
    // data() {
    //     return{
    //         film: [],
    //         series:[]
    //     }
    // },

    // methods:{
    //     getFilm(filmName){
    //         axios.get('https://api.themoviedb.org/3/search/movie?api_key=704bcbb605fa3bbfcf7f5616feaf17bb&query='+filmName)
    //         .then((response) => {
    //             console.log(response);
    //             this.film=response.data.results;
    //         })
    //         .catch(function(error){
    //             console.log(error);
    //         })
    //         .finally(function () {
                
    //         });
    //     },
    //     searchFilm(cercato){
    //         this.getFilm(cercato);
    //         this.getSeries(cercato);
    //         console.log(cercato);
    //     },
    //     getSeries(seriesName){
    //         console.log('&query='+seriesName
    //         );
    //         axios.get('https://api.themoviedb.org/3/search/tv?api_key=704bcbb605fa3bbfcf7f5616feaf17bb&language=it_IT&query='+seriesName)
    //         .then((response) => {
    //             console.log(response);
    //             this.series=response.data.results;
    //         })
    //         .catch(function(error){
    //             console.log(error);
    //         })
    //         .finally(function () {
                
    //         });
    //     },
    // },
}
</script>

<template>
    <nav class="navbar bg-dark  d-flex justify-content-between">
        <div class=" ">
            <a class="navbar-brand text-light ms-2">Boolflix</a>
        </div>
        <AppSearch  @searched="searchFilm" class="me-2"/>
    </nav>
</template>

<style lang="scss" >
@use'../../node_modules/bootstrap/scss/bootstrap.scss';
</style>