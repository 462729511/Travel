<template>
<div>
  <div class="title">热销推荐</div>
  <ul>
    <li class="item" v-for="item in recommendList">
        <img class="item-img" :src="item.imgUrl" alt="">
      <div class="item-info">
        <p class="item-title">{{item.title}}</p>
        <p class="item-desc">{{item.desc}}</p>
        <button class="item-button">查看详情</button>
      </div>
    </li>
  </ul>
</div>
</template>

<script>
export default {
  name:'HomeRecommend',
  data () {
    return {
      recommendList:[
        {
          imgUrl:'http://img1.qunarzz.com/sight/p0/1804/c7/c74a66ec65491fc2a3.img.jpg_200x200_57fd010d.jpg',
          title:'青岛东方影院万达',
          desc:'啦啦啦啦啦啦啦啦啦啦'
        }
      ]
    }
  }
}
</script>
<style lang="stylus" scoped>
  .title
    margin-top: .2rem
    line-height: .8rem
    background: #eee
    text-indent: .2rem
  .item
    overflow: hidden
    display: flex
    height: 1.9rem
    .item-img
      width: 1.7rem
      height: 1.7rem
      padding: .1rem
    .item-info

      padding: .1rem
      min-width: 0
      .item-title
        line-height: .54rem
        font-size: .32rem
        ellipsis()
      .item-desc
        line-height: .4rem
        color: #ccc
        ellipsis()
      .item-button
        line-height: .44rem
        margin-top: .16rem
        background: #ff9300
        padding: 0 .2rem
        border-radius: .06rem
        color: #fff
</style>
