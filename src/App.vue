<template>
    <div>
      <home-header />
      <home-swiper />
      <home-icons />
    </div>
</template>
  
<script setup lang='ts'>
import HomeHeader from './components/Header.vue'
import HomeSwiper from './components/Swiper.vue'
import HomeIcons from './components/Icons.vue'
  export default{
    name:'App',
    components:{
      HomeHeader,
      HomeSwiper,
      HomeIcons
    }
  }
</script>
  
<style>
  
</style>
