<script>
export default {
    data() {
        return{
            
        }
    },
    props: {
        film:{
            type:Array,
            required:true
        }

    }
}
</script>

<template>
    <article v-for="(film, index) in film" :key="index" :film="film">
        <h1>{{ film.original }}</h1>
        <h2> {{ film.original_title }}</h2>
        <p>{{ film.vote_average }}</p> <span> {{ film.original_language }}</span>
    </article>


</template>

<style lang="scss" scoped>
</style>