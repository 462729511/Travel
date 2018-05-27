<template>
<div class="header">
  <router-link to="./">
    <div class="header-left">
      <span class="iconfont back-icon">&#xe624;</span>
    </div>
  </router-link>
  <p class="city-choose">城市选择</p>
</div>
</template>

<script>
export default {
  name:'CityHeader'
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
    text-align center
    position: relative;
    .header-left
      width:.64rem
      color: #fff
      position: absolute;
      left:0
    .city-choose
      margin:0 auto
</style>
