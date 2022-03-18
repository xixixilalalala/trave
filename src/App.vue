<template>
    <div>
      <home-header />
      <home-swiper />
      <home-icons />
      <home-recommend />
      <home-weekend />
    </div>
</template>
  
<script setup lang='ts'>
import HomeHeader from './components/Header.vue'
import HomeSwiper from './components/Swiper.vue'
import HomeIcons from './components/Icons.vue'
import HomeRecommend from './components/Recommend.vue'
import HomeWeekend from './components/Weekend.vue'
  export default{
    name:'App',
    components:{
      HomeHeader,
      HomeSwiper,
      HomeIcons,
      HomeRecommend,
      HomeWeekend
    }
  }
</script>
  
<style>
  
</style>
