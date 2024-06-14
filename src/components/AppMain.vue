<script>
import AppSearch from "./AppSearch.vue";
import axios from "axios";
export default {
    components: {
        AppSearch
    },
    data() {
        return{
            film: []
        }
    },
    methods:{
        getFilm(){
            axios.get('https://api.themoviedb.org/3/search/movie?api_key=704bcbb605fa3bbfcf7f5616feaf17bb&query=+')
            .then((response) => {
                console.log(response.data.data);
                this.film=response.data.data;
            })
            .catch(function(error){
                console.log(error);
            })
            .finally(function () {
                
            });
        },
    },
    created() {
        this.getFilm();
    },
}
</script>

<template>
    <AppSearch/>
<section>
    <h1>main section </h1>
</section>
</template>

<style lang="scss" scoped>
</style>