<template>
	<div class="wrapper">
		<div class="icons">
			<div class="icon" v-for="item of list" :key='item.id'>
				<div class="icon-img">
					<img class="icon-imgContent" :src="item.imgUrl">
				</div>
				<p class="icon-desc">{{item.desc}}</p>
			</div>
		</div>
	</div>
</template>

<script>
export default{
	name:"HomeIcons",
	props: {
		list: Array
	}
}

</script>
<style lang='stylus' scoped="true">
@import '~@/styles/global.styl'
@import '~@/styles/minxins.styl'
	.wrapper
		overflow hidden
		height 0
		width 100%
		padding-bottom 51%
		.icons
			margin-top .1rem
			height 3.9rem
			.icon
				position: relative
				overflow: hidden
				width: 25%
				height: 0
				float:left
				padding-bottom: 25%
				.icon-img
					position absolute
					top 0
					left 0
					right 0
					bottom .44rem
					box-sizing border-box
					padding .1rem
					.icon-imgContent{
						display block
						margin 0 auto
						height 100%
					}
				.icon-desc
					position absolute
					left 0
					right 0
					bottom 0
					height .44rem
					text-align center
					line-height .44rem
					color $textColor
					ellipsis()

</style>