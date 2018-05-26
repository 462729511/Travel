<template>
<div class="icons">
  <swiper :options="swiperOption">
    <swiper-slide class="icons-swiper" v-for="(page,index) in pages" :key="index">
      <div class="icon" v-for="item in page">
        <img class="icon-img" :src="item.iconUrl" alt="">
        <p class="icon-text">{{item.iconText}}</p>
      </div>
    </swiper-slide>
  </swiper>
</div>
</template>

<script>
export default {
  nameL:'Icons',

  data(){
    return{
      swiperOption:{
        pagination:'.swiper-pagination',
      },
      iconList:[
        {
          id:'0',
          iconUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          iconText:'热门景点阿斯顿阿斯顿阿斯顿按时'
        },
        {
          id:'0',
          iconUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          iconText:'热门景点'
        },
        {
          id:'0',
          iconUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          iconText:'热门景点'
        },
        {
          id:'0',
          iconUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          iconText:'热门景点'
        },
        {
          id:'0',
          iconUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          iconText:'热门景点'
        },
        {
          id:'0',
          iconUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          iconText:'热门景点'
        },
        {
          id:'0',
          iconUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          iconText:'热门景点'
        },
        {
          id:'0',
          iconUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          iconText:'热门景点'
        },
        {
          id:'0',
          iconUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          iconText:'热门啊啊'
        },
      ]
    }
  },
  computed:{
    pages (){
      const pages=[]
      this.iconList.forEach((item,index)=>{
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
    padding-bottom 50%
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
