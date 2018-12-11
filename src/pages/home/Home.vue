<!-- 主页大页面，components为组件 -->

<template>
  <div>
  	<home-header></home-header>
  	<home-swiper></home-swiper>
  	<home-icons></home-icons>
  </div>

</template>

<script>
import HomeHeader from './components/HomeHeader'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
export default {
  name: 'Home',
  components:{
  	HomeHeader,
  	HomeSwiper,
  	HomeIcons
  }
}
</script>
<style type="text/css">
</style>
