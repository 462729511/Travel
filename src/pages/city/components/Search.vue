<template>
<div class="search">
  <input class="search-input" type="text" placeholder="输入城市名或拼音">
</div>
</template>

<script>
export default {
  name:'CitySearch'
}
</script>
<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  .search
    background-color $bgColor
    height:.6rem
    padding:0.1rem
    .search-input
      width:100%
      text-align center
      border-radius .06rem
      height:.62rem
      line-height .62rem
</style>
