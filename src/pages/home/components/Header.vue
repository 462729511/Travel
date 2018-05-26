<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont">&#xe624;</span>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe65a;</span>
      入城市/游玩/酒店
    </div>
    <div class="header-right">
      城市
      <span class="iconfont">&#xe6aa;</span>
    </div>
  </div>
</template>

<script>
export default {
  name:'HomeHeader'
}
</script>

<style lang="stylus" scoped>
  .header
    height:.86rem
    display flex
    line-height .86rem
    background:#00bcd4
    color: white
    .header-left
      width:.64rem
      float: left
    .header-input
      flex:1
      background-color #ffffff
      border-radius .1rem
      margin-top .12rem
      height:.64rem
      color: #ccc
      line-height .64rem
    .header-right
      float: right
      width:1.24rem
      text-align center
</style>
