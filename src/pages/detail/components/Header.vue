<template>
	<div>
		<div class="headerAbs" v-show = 'show'>
	  	<router-link tag='div' to='/' class="detail-header-back iconfont">&#xe624;</router-link>
	  </div>
	  <div class="headerFix" v-show = '!show' :style='opacityStyle'>
	  	<router-link to='/'>
	    	<div class="iconfont header-back">&#xe624;</div>
	  	</router-link>
	  	景点详情
	  </div>
	</div>
</template>

<script>

export default {
  name: 'DetailHeader',
  data () {
  	return {
  		show: true,
  		opacityStyle: {
  			opacity: 0
  		}
  	}
  },
  methods:{
  	handleScroll () {
  		const top = document.documentElement.scrollTop
  		// console.log(top)
  		if(top > 0 && top < 150){
  			const opacity = top / 150
  			this.opacityStyle = {
  				opacity
  			}
  			this.show = false
  		}else if(top >= 150){
  			this.show = false
  		}else{
  			this.show = true
  		}
  	}
  },
  mounted () {
  	window.addEventListener('scroll', this.handleScroll)
  },
  beforeDestroy () {
  	window.removeEventListener('scroll', this.handleScroll)
  }

}

</script>
<style lang="stylus" scoped>
	@import "~@/styles/global.styl"
	.headerAbs
		position: absolute
		left: .43rem
		top: .43rem
		.detail-header-back
			color: #fff
			font-size: .4rem
	.headerFix
		position fixed
		z-index: 9
		left 0
		top 0
		right 0
		overflow hidden
		height .86rem
		line-height .86rem
		color #fff
		background blue
		background $bgColor
		text-align  center
		.header-back
			color #fff
			font-size .4rem
			width .64rem
			text-align center
			position absolute

		
</style>