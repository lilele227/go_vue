<template>
  <div class="header">
  	<router-link to='/'>
    	<div class="iconfont header-back">&#xe624;</div>
  	</router-link>
  	城市选择
  </div>

</template>

<script>
export default {
  name: 'CityHeader'
}
</script>
<style lang='stylus' scoped>
@import "~@/styles/global.styl"
		.header
			overflow hidden
			height .86rem
			line-height .86rem
			color #fff
			background blue
			background $bgColor
			text-align  center
			position relative
			.header-back
				color #fff
				font-size .4rem
				width .64rem
				text-align center
				position absolute
				
</style>
