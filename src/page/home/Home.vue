<template>
    <div>
      <home-header />
      <home-swiper :list="swiperList"/>
      <home-icons :list="iconList"/>
      <home-recommend :list="recommendList"/>
      <home-weekend :list="weekendList"/>
    </div>
</template>
  
<script>
import HomeHeader from './components/Header.vue'
import HomeSwiper from './components/Swiper.vue'
import HomeIcons from './components/Icons.vue'
import HomeRecommend from './components/Recommend.vue'
import HomeWeekend from './components/Weekend.vue'
import axios from 'axios'
import {mapState} from 'vuex'
  export default{
    name:'homeComponent',
    components:{
      HomeHeader,
      HomeSwiper,
      HomeIcons,
      HomeRecommend,
      HomeWeekend
    },
    data (){
      return{
        lastCity:'',
        swiperList:[],
        iconList:[],
        recommendList:[],
        weekendList:[]
      }
    },
    computed:{
      ...mapState(['city'])
    },
    methods:{
      getHomeInfo(){
        axios.get('/mock/index.json?city=' + this.city)
        .then(this.getHomeInfoSucc)
      },
      getHomeInfoSucc (res){
        res=res.data
        if(res.ret && res.data){
          const data=res.data
          this.swiperList=data.swiperList
          this.iconList=data.iconList
          this.recommendList=data.recommendList
          this.weekendList=data.weekendList
        }
    }
    },
    
    mounted (){
      this.lastCity=this.city
      this.getHomeInfo()
    },
    activated(){
      if(!(this.lastCity === this.city)) {
        this.lastCity=this.city
        this.getHomeInfo()
      }
    }
  }
</script>
  
<style>
  
</style>
