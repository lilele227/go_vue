<template>
	<div>
	  <detail-banner  :sightName = "sightName" :bannerImg = "bannerImg" :GallaryImgs = "GallaryImgs"></detail-banner>
	  <detail-header></detail-header>
	  <detail-list	:categoryList = "categoryList"
	  ></detail-list>
	  <div class="content"></div>
	</div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import axios from 'axios'
export default {
  name: 'Detail',
  data () {
  	return {
  		sightName: '',
  		bannerImg: '',
  		GallaryImgs: [],
  		categoryList: []
  	}
  },
  components: {
  	DetailBanner,
  	DetailHeader,
  	DetailList
  },
  methods: {
  	getDetailInfo() {
  		axios.get('/api/detail.json').then(this.handleData)
  	},
  	handleData(res){
  		res = res.data
  		// console.log(res)
  		if (res.ret && res.data) {
  			const data = res.data
  			this.sightName = data.sightName
  			this.bannerImg = data.bannerImg
  			this.GallaryImgs = data.GallaryImgs
  			this.categoryList = data.categoryList
  			// console.log(this.sightName,this.bannerImg,this.GallaryImgs,this.categoryList)
  			
  		}
  	}
  },
  mounted () {
  	this.getDetailInfo()
  }
}
</script>
<style lang="stylus" scoped>
	.content
		height: 50rem

</style>
