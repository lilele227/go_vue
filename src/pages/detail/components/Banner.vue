<template>
	<div>
	  <div class="banner" @click='BannerClick'>
	  	<img class="banner-img" :src="bannerImg">
	  	<div class="banner-info">
	  		<div class="banner-number">
	  			<span class="banner-icon iconfont">&#xe604;</span>
	  			{{this.GallaryImgs.length}}
	  		</div>
	  		<div class="banner-titile">
	  			{{this.sightName}}
	  		</div>
	  	</div>
	  </div>
	  <common-gallary @close='GallaryClose' v-show='showGallary' :imgs='GallaryImgs'></common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  props: {
  	  sightName: String,
      bannerImg: String,
      GallaryImgs: Array
  },
  data () {
  	return {
  		showGallary: false
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
        background: rgba(0, 0, 0, .3)
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