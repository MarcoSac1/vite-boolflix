<script>
export default {
    data() {
        return{
            cercato: '',

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
        <form class="d-flex col-8" role="search">
                <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search" v-model="cercato" >
                <button class="btn btn-outline-danger" type="button" @click="$emit('searched', cercato)">Search</button>
        </form>
    </nav>

<!-- <input type="text" v-model="cercato"> -->
<!-- <button type="button" @click="$emit('searched', cercato)">search</button> -->
</template>

<style lang="scss" scoped>

</style>