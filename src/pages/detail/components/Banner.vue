<template>
  <div class="banner">
  	<img class="banner-img" src="//img1.qunarzz.com/wugc/p102/201301/13/20805c2d8250fd1b93835fbb.jpg_600x330_a55ba2ef.jpg">
  	<span class="banner-back iconfont">&#xe624;</span>
  	<div class="banner-info">
  		<div class="banner-number">
  			<span class="banner-icon iconfont">&#xe604;</span>
  			9
  		</div>
  		<div class="banner-titile">
  			外滩
  		</div>
  	</div>
  </div>

</template>

<script>
export default {
  name: 'DetailBanner',

}
</script>
<style lang="stylus" scoped>
  .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img
      width: 100%
    .banner-back
    	position: absolute
    	left: .2rem
    	top: .2rem
    	color: #fff
    .banner-info
      display: flex
      flex-direction: column
      position: absolute
      left: 0
      right: 0
      bottom: 0
      line-height: .6rem
      color: #fff
      .banner-titile
        flex: 1
        font-size: .32rem
        padding: 0 .2rem
      .banner-number
        height: .32rem
        line-height: .32rem
        margin-top: .14rem
        padding: 0 .4rem
        border-radius: .2rem
        font-size: .24rem
        .banner-icon
          font-size: .24rem
</style>