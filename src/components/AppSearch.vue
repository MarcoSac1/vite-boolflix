<script>
export default {
    data() {
        return{
            
        }
    },
    props: {


    }
}
</script>

<template>
<h1>search bar section</h1>

<input type="text" v-model="cercato">
<button type="button" @click="$emit('searched', cercato)">search</button>
</template>

<style lang="scss" scoped>
</style>