<template>
    <div>
        <city-header></city-header>
        <city-search></city-search>
        <city-list
        :cities="cities"
        :hot="hotCities"
        :letter="letter"></city-list>
        <city-Alpahbet
        :cities="cities"
        @change="handleLetterChange"></city-Alpahbet>
    </div>
</template>
<script>
/* eslint-disable */
import axios from 'axios'
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlpahbet from './components/Alpahbet'
export default {
  name: 'city',
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlpahbet
  },
  data () {
      return {
          cities: {},
          hotCities: [],
          letter: ''
      }
  },
  methods: {
      handleLetterChange(letter) {
          this.letter = letter
      },
      getCityInfo () {
          axios.get('/api/city.json')
            .then(this.handleGetCityInfoSucc)
      },
      handleGetCityInfoSucc (res) {
          res = res.data
          if (res.ret && res.data) {
             const data = res.data
             this.cities = data.cities
             this.hotCities = data.hotCities
          }

      }
  },
  mounted () {
      this.getCityInfo()
  }
}
</script>
<style lang='stylus' scoped>
</style>
