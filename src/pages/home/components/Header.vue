<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont back-icon">&#xe624;</span>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe65a;</span>
      入城市/游玩/酒店
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{this.city}}
        <span class="iconfont">&#xe6aa;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
  import {mapState} from 'vuex'
export default {
  name:'HomeHeader',
  computed:{
    ...mapState(['city'])
  },
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  .header
    height:.86rem
    display flex
    line-height .86rem
    background:$bgColor
    color: white
    .header-left
      width:.64rem
      float: left
      .back-icon
        display block
        text-align center
        font-size.4rem
    .header-input
      flex:1
      background-color #ffffff
      border-radius .1rem
      margin-top .12rem
      height:.64rem
      color: #ccc
      line-height .64rem
    .header-right
      min-width 1.24rem
      padding: .05rem
      float: right
      text-align center
      color: #fff
</style>
