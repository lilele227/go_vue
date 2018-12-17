<template>
	<div>
	  <div class="banner" @click='BannerClick'>
	  	<img class="banner-img" src="//img1.qunarzz.com/wugc/p102/201301/13/20805c2d8250fd1b93835fbb.jpg_600x330_a55ba2ef.jpg">
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
	  <common-gallary @close='GallaryClose' v-show='showGallary' :imgs='imgs'></common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  props: {
  	
  },
  data () {
  	return {
  		showGallary: false,
  		imgs:['http://img1.qunarzz.com/sight/p0/1704/c9/c936f3fccfc6d7eda3.img.jpg_r_800x800_93bf62f1.jpg','http://img1.qunarzz.com/sight/p0/1704/6b/6b527e63ce7fee86a3.img.jpg_r_800x800_9d4d911c.jpg']
  	}
  },
  methods: {
  	GallaryClose () {
  		this.showGallary = false
  	},
  	BannerClick () {
  		this.showGallary = true
  	}
  },
  components: {
  	CommonGallary
  }
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