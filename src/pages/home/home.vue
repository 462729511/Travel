<template>
  <div>
      <home-header></home-header>
      <home-swiper></home-swiper>
    <icons></icons>
    <home-recommend></home-recommend>
    <home-weekend></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import Icons from './components/Icons'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'
export default {
    name:'home',
    components:{
      HomeHeader,
      HomeSwiper,
      Icons,
      HomeRecommend,
      HomeWeekend
    }
}
</script>
<style>

</style>
