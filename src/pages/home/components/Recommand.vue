<template>
	<div>
		<div class="title">热销推荐</div>
		<ul>
			<li class="item" v-for='item of list' :key='item.id'>
				<div class="item-img-wrapper">
					<img class="item-img" :src="item.imgUrl">
				</div>
				<div class="item-info">
					<p class="item-title">{{item.title}}</p>
					<p class="item-desc">{{item.desc}}</p>
					<button class="item-button">查看详情</button>
				</div>
			</li>
		</ul>
	</div>
</template>

<script>
export default {
	name: 'HomeRecommand',
	props: {
		list: Array
	}
}

</script>

<style lang="stylus" scoped="true">
@import '~@/styles/minxins.styl'
	.title
		margin-top .2rem
		line-height .8rem
		text-indent .2rem
		background #eee
	.item
		overflow hidden
		display flex
		height 1.9rem
		border-bottom .02rem solid #ccc
		.item-img
			width 1.7rem
			height 1.7rem
			padding .1rem
		.item-info
			flex 1
			padding .1rem
			width 0
			.item-title
				line-height .54rem
				font-size .32rem
				ellipsis()
			.item-desc
				line-height .4rem
				color #ccc
				ellipsis()
			.item-button
				// line-height .44rem
				margin-top .28rem
				background #ff9300
				padding .1rem
				border-radius .06rem
				color #fff
</style>