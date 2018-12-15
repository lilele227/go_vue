<template>
  <ul class="list">
    <li 
      class="item" 
      v-for='item in letters'
      :key='item'
      :ref='item'
      @click='letterClick' 
      @touchstart='handleTouchStart'
      @touchmove='handleTouchMove'
      @touchend='handleTouchEnd'
    >
    {{item}}
    </li>
  </ul>
</template>

<script>
export default {
  name: 'CityLetter',
  props: {
    cityList: Array
    },
  data () {
    return {
      touchStatus: false
    }
  },
  computed: {
    letters () {
      const letters = []
      for(let i=0;i<this.cityList.length;i++) {
        letters.push(this.cityList[i].initial)
      }
      return letters
    }
  },
  methods: {
    letterClick (e) {
      this.$emit('change',e.target.innerText)

    },
    handleTouchStart () {
      this.touchStatus = true
    },
    handleTouchMove (e) {
      if(this.touchStatus){
        const startY = this.$refs['A'][0].offsetTop
        const endY = e.changedTouches[0].clientY - 79
        const touchRange = endY-startY
        const index = Math.floor(touchRange/20)
        if(index >= 0 && index < this.letters.length){
          this.$emit('change',this.letters[index])
        }
      }
    },
    handleTouchEnd () {
      this.touchStatus = false
    }
  },

}
</script>

<style lang="stylus" scoped>
  @import "~@/styles/global.styl"
  .list
    display: flex
    flex-direction: column
    justify-content: center
    position: absolute
    right: 0
    top: 1.58rem
    bottom: 0
    width: .4rem
    .item
      line-height: .4rem
      text-align: center
      color: $bgColor
</style>
