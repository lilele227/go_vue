<template>
<div class="wrapper">
  <swiper :options="swiperOption">
    <!-- slides -->
    <swiper-slide v-for='item of swiperList' :key = 'item.id'>
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
  data (){
  	return {
  		swiperOption: {
  			pagination: '.swiper-pagination',
  			loop: true
  		},
  		swiperList: [{
  			id: '0001',
  			imgUrl: '//gw.alicdn.com/tfs/TB1Yla5upYqK1RjSZLeXXbXppXa-1125-352.jpg_790x10000Q75.jpg_.webp'
  		},{
  			id: '0002',
  			imgUrl: '//gw.alicdn.com/tfs/TB1Yla5upYqK1RjSZLeXXbXppXa-1125-352.jpg_790x10000Q75.jpg_.webp'
  		},{
  			id: '0003',
  			imgUrl: '//gw.alicdn.com/tfs/TB1Yla5upYqK1RjSZLeXXbXppXa-1125-352.jpg_790x10000Q75.jpg_.webp'
  		}]
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