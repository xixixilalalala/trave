<template>
<div>
    <city-header />
    <city-search />
    <city-list :cities="cities" :hot="hotCities"/>
    <city-alphabet :cities="cities"/>
</div>
</template>

<script>
import axios from 'axios'
    import CityHeader from './components/Header.vue'
    import CitySearch from './components/Search.vue'
    import CityList from './components/List.vue'
    import CityAlphabet from './components/Alphabet.vue'
    export default {
        name: 'MyCity',
        components:{
            CityHeader,
            CitySearch,
            CityList,
            CityAlphabet
        },
        data (){
            return{
                cities:{},
                hotCities:[],
            }
        },
        methods:{
            getCityInfo (){
                axios.get('/mock/city.json')
                .then(this.handleGetCityInfoSucc)
            },
            handleGetCityInfoSucc(res){
                res=res.data
                if(res.ret && res.data){
                    const data=res.data
                    this.cities=data.cities
                    this.hotCities=data.hotCities
                }
            }
        },
        mounted (){
            this.getCityInfo()
        }
    }
</script>

<style lang="stylus" scoped>

</style>