<template>
  <div class="header">
    <div class="header-left">搜索</div>
    <div class="header-input">123</div>
    <div class="header-right">城市</div>
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
    background:#00bcd4
    .header-left
      width:.64rem
      float: left
    .header-input
      flex:1
    .header-right
      float: right
      width:1.24rem
</style>
