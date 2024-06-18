<script>
import AppSearch from './AppSearch.vue';

export default {
    components:{
        AppSearch
    },
    data() {
        return{
            
        }
    },
    props: {


    }
}
</script>

<template>
    <nav class="navbar bg-dark  d-flex justify-content-between">
        <div class=" ">
            <a class="navbar-brand text-light ms-2">Boolflix</a>
        </div>
        <AppSearch class="me-2"/>
    </nav>
</template>

<style lang="scss" >
@use'../../node_modules/bootstrap/scss/bootstrap.scss';
</style>