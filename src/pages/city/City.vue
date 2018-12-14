<template>
	<div>
		<city-header></city-header>
 		<city-search></city-search>
 		<city-list :city='citynow' :hotcity='hotcity' :cityList='cityList'></city-list>
 		<city-letter :cityList='cityList'></city-letter>
	</div>


</template>

<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityLetter from './components/Letter'
import axios from "axios"
export default {
  name: 'City',
  components: {
  	CityHeader,
  	CitySearch,
  	CityList,
  	CityLetter
  },
  data () {
  	return {
  		citynow: '',
  		hotcity:[],
  		cityList:[]
  	}
  },
  methods: {
  	getCityInfo(){
  		axios.get('/api/city.json').then(this.getCityInfoSucc)
  	},
  	getCityInfoSucc(res){
  		res = res.data
  		if(res.ret && res.data){
  			res = res.data
  			this.citynow = res.citynow
  			this.hotcity = res.hotcity
  			this.cityList = res.cityList
  			console.log(this.cityList[0].list)

  		}
  	}
  },
  mounted () {
  	this.getCityInfo()
  }

}
</script>
<style>

</style>
