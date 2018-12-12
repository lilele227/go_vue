<!-- 主页大页面，components为组件 -->

<template>
  <div>
  	<home-header :city='city'></home-header>
  	<home-swiper :list='swiperList'></home-swiper>
    <home-icons :list='iconList'></home-icons>
    <home-recommand :list='recommendList'></home-recommand>
  	<home-around :list='aroundList'></home-around>

  </div>

</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecommand from './components/Recommand'
import HomeAround from './components/Around'
import axios from "axios"
export default {
  name: 'Home',
  components:{
  	HomeHeader,
  	HomeSwiper,
  	HomeIcons,
    HomeRecommand,
    HomeAround
  },
  data () {
    return {
      city: '',
      swiperList: [],
      iconList: [],
      recommendList: [],
      aroundList: []
    }
  },
  methods: {
    getHomeInfo(){
      axios.get('/api/index.json')
      .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if(res.ret && res.data)
        this.city = res.data.city
        this.swiperList = res.data.swiperList
        this.iconList = res.data.iconList
        this.recommendList = res.data.recommendList
        this.aroundList = res.data.aroundList

    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>
<style type="text/css">
</style>
