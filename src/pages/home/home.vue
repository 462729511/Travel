<template>
  <div>
      <home-header></home-header>
      <home-swiper v-bind:list="swiperList"></home-swiper>
    <icons :list="iconList"></icons>
    <home-recommend :list="recommendList"></home-recommend>
    <home-weekend :list="weekendList"></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import Icons from './components/Icons'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'
import axios from 'axios'
export default {
    name:'home',
    components:{
      HomeHeader,
      HomeSwiper,
      Icons,
      HomeRecommend,
      HomeWeekend
    },
  data () {
    return {
      iconList:[],
      recommendList:[],
      swiperList:[],
      weekendList:[]
    }
  },
  methods:{
    getHomeInfo () {
      axios.get('/static/mock/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc(res) {
      res =res .data
      if(res.ret && res.data){
        this.iconList=res.data.iconList
        this.recommendList=res.data.recommendList
        this.swiperList=res.data.swiperList
        this.weekendList=res.data.weekendList
      }
      console.log(res)
    }
  },
  mounted () {
      this.getHomeInfo()
  }
}
</script>
<style>

</style>
