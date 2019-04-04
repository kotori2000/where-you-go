<template>
  <div>
      <div class="search">
          <input type="text" v-model="keyword" class="search-input" placeholder="输入城市名或拼音" />
      </div>
      <div class="search-content" ref="search" v-show="keyword">
        <ul>
          <li class="search-item border-bottom" v-for="(item, index) in list" :key="index">{{item.name}}</li>
          <li class="search-item border-bottom" v-show="!list.length">没有找到匹配数据</li>
        </ul>
      </div>
  </div>
</template>
<script>
/* eslint-disable */
import Bscroll from 'better-scroll'
export default {
  name: 'CitySearch',
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  watch: {
    keyword () {
      if(this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return this.list
      }
      this.timer = setTimeout(() => {
        const result = []
        for(let i in this.cities) {
          this.cities[i].forEach((value) => {
            if(value.spell.indexOf(this.keyword) > -1 || 
            value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 50)
    }
  },
  props: {
    cities: Object
  },
  mounted() {
    this.scroll = new Bscroll(this.$refs.search)
  }
}
</script>
<style lang='stylus' scoped>
  @import '~styles/varibles.styl'
  .search
    height: .72rem
    padding: 0 .1rem
    background: $bgColor
    .search-input
        box-sizing: border-box
        width: 100%
        padding: 0 .1rem
        height: .62rem
        line-light: .62rem
        text-align: center
        border-radius: .06rem
        color: #666
  .search-content
    z-index: 1
    overflow: hidden
    position: absolute
    width:100%
    top: 1.58rem
    left: 0
    rigth: 0
    bottom: 0
    background: #cccccc
    .search-item
      line-height: .62rem
      padding-left: .2rem
      color: #666
      background: #ffffff
      .border-bottom
        &:before
          border-color: #000
        &:after
          border-color: #000
</style>
