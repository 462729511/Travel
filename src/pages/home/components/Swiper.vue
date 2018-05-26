<template>
  <div class="wraper" >
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item of swiperList" :v-key="item.id">
        <img class="swiper-img" :src="item.imgUrl" alt="">
      </swiper-slide>

      <!-- Optional controls -->
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>

</template>

<script>
export default {
  name:'HomeSwiper',
  data:function () {
    return{
      swiperOption:{
        pagination:'.swiper-pagination',
        clickable:true,
        loop:true,
        autoplay:{
          stopOnLastSlide:true
        }
      },
      swiperList:[
        {
        id:0,
        imgUrl:'http://img1.qunarzz.com/piao/fusion/1805/e5/59fad13a64807d02.jpg_750x200_713ae984.jpg'
      },
        {
          id:1,
          imgUrl:'http://img1.qunarzz.com/piao/fusion/1805/77/f63bd04dd5319602.jpg_750x200_6ba8e0ca.jpg'
        }
      ]
    }
  }
}
</script>
<style lang="stylus" scoped>

  .wraper
    overflow hidden
    width: 100%
    height:0
    padding-bottom:31.25%
    .swiper-img
      width: 100%
</style>
