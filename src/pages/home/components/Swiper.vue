<template>
  <div class="wraper" >
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item of list" :v-key="item.id">
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
  props:{
    list:Array
  },
  data:function () {
    return{
      swiperOption:{
        pagination:'.swiper-pagination',
        clickable:false,
        loop:true,
        autoplay:true
      },
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
