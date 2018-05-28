<template>
  <ul class="list" ref="wrapper" >
   <li class="item"
       v-for="item of letters"
       :key="item"
       :ref="item"
       @click="handleLetterClick"
       @touchstart="handleTouchStart"
       @touchmove="handleTouchMove"
       @touchend="handleTouchEnd"
   >{{item}}</li>
  </ul>
</template>

<script>
  export default {
    name:'CityAlphabet',
    data () {
      return {
        touchStatus:false
      }
    },
    computed: {
      letters () {
        const letters=[]
        for(let i in this.cities){
          letters.push(i)
        }
        return letters
        console.log(letters)
      }
    },
    props:{
      cities:Object
    },
    methods:{
      handleLetterClick (e) {
        this.$emit('change',e.target.innerHTML)
      },
      handleTouchStart () {
        this.touchStatus=true
      },
      handleTouchMove (e) {
        if(this.touchStatus){
          const startY=this.$refs['A'][0].offsetTop
          const touchY=e.touches[0].clientY -83
          const index=Math.floor((touchY-startY)/20)
         if(index >=0 && index <this.letters.length){
            this.$emit('change',this.letters[index])
         }
        }
      },
      handleTouchEnd () {
        this.touchStatus =false
      }
    }
  }
</script>
<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .list
    position: absolute;
    top:1.58rem
    right:0
    bottom:0
    width:.4rem
    display: flex
    justify-content center
    flex-direction column
    .item
      line-height: .4rem
      text-align: center
      color: $bgColor
</style>
