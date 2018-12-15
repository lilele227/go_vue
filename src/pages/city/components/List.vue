<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wraper">
            <div class="button">{{this.city}}</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wraper" v-for="item of hotcity">
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area" id="area" v-for='item,key in cityList' :key='key' :ref='key'>
        <div class="title border-topbottom">{{item.initial}}</div>
        <div class="item-list">
          <div class="item border-bottom" v-for='city,cindex in cityList[key].list' :key='cindex'>{{city.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CityList',
  props:{
    city: String,
    hotcity: Array,
    cityList: Array,
    letter: String

  },
  mounted () {
  	this.scroll = new Bscroll(this.$refs.wrapper)
  },
  watch: {
    letter () {
      if(this.letter){
        const areaIndex = this.letter.charCodeAt()-65
        const element = this.$refs[areaIndex][0]
        this.scroll.scrollToElement(element)
      }
      
    }
  }
}
</script>
<style lang="stylus" scoped>
  @import "~@/styles/global.styl"
  .list
    overflow: hidden
    position: absolute
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    .title
      line-height: .54rem
      background: #eee
      padding-left: .2rem
      color: #666
      font-size: .26rem
    .button-list
      overflow: hidden
      padding: .1rem .6rem .1rem .1rem
      .button-wraper
        float:left
        width: 33.33%
        .button
          margin: .1rem
          padding: .1rem 0
          text-align: center
          border: .02rem solid #ccc
          border-radius: .06rem
    .item-list
      .item
        line-height: .76rem
        padding-left: .2rem
</style>
