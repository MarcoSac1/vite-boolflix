<script>
import AppSearch from "./AppSearch.vue";
import axios from "axios";
import CardFilm from "./CardFilm.vue";
export default {
    components: {
        AppSearch,
        CardFilm
    },
    data() {
        return{
            film: [],
            series:[]
        }
    },

    methods:{
        getFilm(filmName){
            axios.get('https://api.themoviedb.org/3/search/movie?api_key=704bcbb605fa3bbfcf7f5616feaf17bb&query='+filmName)
            .then((response) => {
                console.log(response);
                this.film=response.data.results;
            })
            .catch(function(error){
                console.log(error);
            })
            .finally(function () {
                
            });
        },
        searchFilm(cercato){
            this.getFilm(cercato);
            this.getSeries(cercato);
            console.log(cercato);
        },
        getSeries(seriesName){
            console.log('&query='+seriesName
            );
            axios.get('https://api.themoviedb.org/3/search/tv?api_key=704bcbb605fa3bbfcf7f5616feaf17bb&language=it_IT&query='+seriesName)
            .then((response) => {
                console.log(response);
                this.series=response.data.results;
            })
            .catch(function(error){
                console.log(error);
            })
            .finally(function () {
                
            });
        },
    },
    created() {
        
    },
}
</script>

<template >
    <div class="bg-dark text-light  ">
        <AppSearch @searched="searchFilm"/>
        <CardFilm :film="film" :series="series" />
    </div>
</template>

<style lang="scss" >
@use'../node_modules/bootstrap/scss/bootstrap.scss';
@use'../styles/partials/variables' as *;
@use'../styles/partials/mixins' as *;
@use'../styles/general.scss';
</style>