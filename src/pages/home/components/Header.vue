<!-- 主页大页面，components为组件 -->

<template>
  <div class="header">
    <div class="header-left">
    	<div class="iconfont backIcon" >&#xe624;</div>
    </div>
    <div class="header-input">
    <span class="iconfont">&#xe632;</span>
    输入城市/景点/游玩主题
  	</div>
  	<router-link to="/city">
	    <div class="header-right">{{this.city}}
	    	<span class="iconfont arrowDown">&#xe62d;</span>
	    </div>
    </router-link>
  </div>

</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
  	city: String
  }
}
</script>
<style lang="stylus" scoped>
@import '~@/styles/global.styl'
	.header
		background: $bgColor
		display:flex
		line-height: .86rem
		color:#fff
		.header-left
			width: .64rem
			.backIcon
				text-align: center
				font-size: .4rem
		.header-input
			flex: 1
			line-height: .64rem
			height: .64rem
			margin-top: .12rem
			margin-left: .2rem
			padding-left: .2rem
			background: #fff
			border-radius: .1rem
			color: #ccc
			
		.header-right
			color: #fff
			text-align: center
			width:1.24rem
			.arrowDown
				margin-left: -.04rem
				font-size: .24rem


</style>
