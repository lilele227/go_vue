<template>
  <ul class="list">
    <li class="item" v-for='item in cityList' @click='letterClick'>
    {{item.initial}}
    </li>
  </ul>
</template>

<script>
export default {
  name: 'CityLetter',
  props: {
    cityList: Array
    },
  methods: {
    letterClick (e) {
      this.$emit('change',e.target.innerText)
    }
  }
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
