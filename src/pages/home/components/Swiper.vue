<template>
<div class="wrapper">
  <swiper :options="swiperOption">
    <!-- slides -->
    <swiper-slide v-for='item of list' :key = 'item.id'>
    	<img class="swiper-img" :src="item.imgUrl">
    </swiper-slide>
    <!-- Optional controls -->
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
</div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    list: Array
  },
  data (){
  	return {
  		swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      }
  	}
  }

}

</script>

<style lang = 'stylus' scoped="true">
	.wrapper >>> .swiper-pagination-bullet-active
		background: #fff !important
	.wrapper
		overflow: hidden
		width: 100%
		height: 0
		padding-bottom: 31.2%

		.swiper-img
			width: 100%

</style>