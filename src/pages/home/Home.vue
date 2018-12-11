<!-- 主页大页面，components为组件 -->

<template>
  <div>
  	<home-header></home-header>
  	<home-swiper></home-swiper>
    <home-icons></home-icons>
    <home-recommand></home-recommand>
  	<home-weekend></home-weekend>

  </div>

</template>

<script>
import HomeHeader from './components/HomeHeader'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecommand from './components/Recommand'
import HomeWeekend from './components/Weekend'
export default {
  name: 'Home',
  components:{
  	HomeHeader,
  	HomeSwiper,
  	HomeIcons,
    HomeRecommand,
    HomeWeekend
  }
}
</script>
<style type="text/css">
</style>
