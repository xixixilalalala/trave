<template>
<div>
    <city-header />
    <city-search />
</div>
</template>

<script setup lang='ts'>
    import CityHeader from './components/Header.vue'
    import CitySearch from './components/Search.vue'
    export default {
        name: 'City',
        components:{
            CityHeader,
            CitySearch
        }
    }
</script>

<style lang="status" scoped>

</style>