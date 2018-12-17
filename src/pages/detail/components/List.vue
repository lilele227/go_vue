<template>
	<div>
		<div class="item" v-for="(item,index) of categoryList" :key='index'>
			<div class="item-title border-bottom">
				<span class="item-title-icon"></span>
				{{item.title}}
			</div>
			<div v-if='item.children'>
				<detail-list :categoryList='item.children' class='item-children'></detail-list>
			</div>
		</div>
	</div>
</template>

<script>

export default {
  name: 'DetailList',
  props: {
		categoryList: Array
  }
}

</script>
<style lang="stylus" scoped>
			.item-title-icon
				position: relative
				z-index: 2
				display: inline-block;
				width: .36rem;
				height: .36rem;
				top: .1rem;
				left: .1rem;
				background: url(//s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat;
				margin-right: .1rem;
				background-size: .4rem 3rem;
			.item-children
				padding: 0 .2rem
</style>