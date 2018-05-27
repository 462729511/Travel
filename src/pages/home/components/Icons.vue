<template>
<div class="icons">
  <swiper :options="swiperOption">
    <swiper-slide class="icons-swiper" v-for="(page,index) in pages" :key="index">
      <div class="icon" v-for="item in page">
        <img class="icon-img" :src="item.imgUrl" alt="">
        <p class="icon-text">{{item.desc}}</p>
      </div>
    </swiper-slide>
  </swiper>
</div>
</template>

<script>
export default {
  nameL:'Icons',
  props:{
    list:Array
  },
  data(){
    return{
      swiperOption:{
        pagination:'.swiper-pagination',
      },

    }
  },
  computed:{
    pages (){
      const pages=[]
      this.list.forEach((item,index)=>{
        const page=Math.floor(index/8)
        if(!pages[page]){
          pages[page]=[]
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>
<style lang="stylus" scoped>
  @import "~styles/mixins.styl"
  .icons
    overflow: hidden
    height:0
    padding-bottom 44%
    margin-top .2rem
    .icons-swiper
      display flex
      flex-wrap wrap
    .icon
      width:25%
      margin-bottom .4rem
      .icon-img
        display: block
        width: 60%
        margin:0 auto
      .icon-text
        text-align center
        ellipsis()
</style>
