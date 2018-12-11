<!-- 主页大页面，components为组件 -->

<template>
  <div>
  	<home-header></home-header>
  	<home-swiper></home-swiper>
  </div>

</template>

<script>
import HomeHeader from './components/HomeHeader'
import HomeSwiper from './components/Swiper'
export default {
  name: 'Home',
  components:{
  	HomeHeader,
  	HomeSwiper
  }
}
</script>
<style type="text/css">
</style>
