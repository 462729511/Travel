<template>
<div>
  <div class="search">
    <input v-model="keyword" class="search-input" type="text" placeholder="输入城市名或拼音">
  </div>
  <div class="search-content" ref="search" v-show="keyword">
    <ul>
      <li class="search-item border-bottom" v-for="item in list" :key="item.id" @click="handleCityClick(item.name)">
        {{item.name}}
      </li>
      <li class="search-item border-bottom" v-show="hasNodata">
        没有找到匹配城市
      </li>
    </ul>
  </div>
</div>

</template>

<script>
  import Bscroll from 'better-scroll'
  import {mapState , mapMutations } from 'vuex'
export default {
  name:'CitySearch',
  props:{
    cities:Object
  },
  data () {
    return {
      keyword:'',
      list:[],
      timer:null
    }
  },
  computed: {
    hasNodata () {
      return !this.list.length
    },
    ...mapState(['city'])
  },
  watch: {
    keyword () {
      if(this.timer) {
        clearTimeout(this.timer)
      }
      if(!this.keyword){
        this.list=[]
        return
      }
      this.timer = setTimeout(()=>{
        const result=[]
        for(let i in this.cities){
          this.cities[i].forEach((value)=>{
            if(value.spell.indexOf(this.keyword)>-1 || value.name.indexOf(this.keyword)>-1){
              result.push(value)
            }
          })
        }
        this.list=result
      },100)
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  },
  methods: {
    handleCityClick (city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  }
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
  .search-content
    z-index 1
    overflow hidden
    position: absolute
    top:1.5rem
    left:0
    right: 0
    bottom: 0
    background: #eee
    .search-item
      line-height .62rem
      padding-left .2rem
      color: #666
      background-color #fff
</style>
