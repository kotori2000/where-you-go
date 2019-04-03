<template>
    <div>
        <city-header></city-header>
        <city-search></city-search>
        <city-list></city-list>
        <city-Alpahbet></city-Alpahbet>
    </div>
</template>
<script>
/* eslint-disable */
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

  }
}
</script>
<style lang='stylus' scoped>
</style>
