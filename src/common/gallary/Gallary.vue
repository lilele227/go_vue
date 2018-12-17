<template>
  <div class="container" @click='ContainerClick'>
		<div class="wrapper">
		  <swiper  :options='swiperOptions'>
		    <!-- slides -->
		    <swiper-slide v-for='(item,index) in imgs' :key='index'>
		    	<img class="swiper-img" :src="item">
		    </swiper-slide>
		    <!-- Optional controls -->
		    <div class="swiper-pagination"  slot="pagination"></div>
		  </swiper>
		</div>
  </div>
</template>

<script>
export default {
  name: 'CommonGallary',
  props: {
  	imgs: Array
  	},
	data () {
		return {
			swiperOptions: {
				pagination: '.swiper-pagination',
				paginationType: 'fraction',
				observer:true,
				observeParents:true
				}
			}
		},
		methods: {
			ContainerClick () {
				this.$emit('close')
			}
		}
	}
</script>

<style lang="stylus" scoped>
	.container >>> .swiper-container
		overflow: visible
	.container
		display: flex
		position: fixed
		z-index: 99
		flex-direction: column
		justify-content: center
		background: #000
		left: 0
		top: 0
		right: 0
		bottom: 0
		.wrapper
			width: 100%
			height: 0
			padding-bottom: 100%
			.swiper-img
				width: 100%
		.swiper-pagination
			color: #fff
			bottom: -1rem

		
</style>
