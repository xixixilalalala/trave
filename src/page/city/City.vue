<template>
<div>
    <city-header />
    <city-search />
    <city-list />
    <city-alphabet />
</div>
</template>

<script setup lang='ts'>
    import CityHeader from './components/Header.vue'
    import CitySearch from './components/Search.vue'
    import CityList from './components/List.vue'
    import CityAlphabet from './components/Alphabet.vue'
    export default {
        name: 'City',
        components:{
            CityHeader,
            CitySearch,
            CityList,
            CityAlphabet
        }
    }
</script>

<style lang="status" scoped>

</style>