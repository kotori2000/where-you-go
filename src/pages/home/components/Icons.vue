<template>
    <div class="icons">
        <swiper>
            <swiper-slide v-for="(page, index) of pages" :key="index">
                <div class="icon" v-for="item in page" :key="item.id">
                    <div class="icon-img">
                        <img class="icon-img-content" :src="item.url">
                    </div>
                    <p class="icon-desc">{{ item.desc }}</p>
                </div>
            </swiper-slide>
        </swiper>
    </div>
</template>
<script>
/* eslint-disable */
export default {
  name: 'HomeIcons',
  data () {
      return{
          iconList: [{
              id: '001',
              url: 'https://imgs.qunarzz.com/vc/a9/04/30/2aefd5c3218d1ba5edd9e51d06.jpg_92.jpg',
              desc: '景点门票'
          },
          {
              id: '002',
              url: 'https://imgs.qunarzz.com/vc/af/93/7f/f9d48adcb5289bfeb41201e976.jpg_92.jpg',
              desc: '海洋馆'
          },
          {
              id: '003',
              url: 'https://img1.qunarzz.com/p/tts5/1706/34/807c23a2ac685202.jpg_r_240x160x90_00858d77.jpg',
              desc: '地铁口的二狗子们'
          },
          {
              id: '004',
              url: 'https://imgs.qunarzz.com/vc/c0/09/99/779471698eb8d00bb19fe8501b.jpg_92.jpg',
              desc: '圣灵公园'
          },
          {
              id: '005',
              url: 'https://imgs.qunarzz.com/vc/e7/ef/a4/c5e9c33cd0a956e59a7d94f055.jpg_92.jpg',
              desc: '东方明珠'
          },
          {
              id: '006',
              url: 'https://imgs.qunarzz.com/vc/ac/3b/35/fb0466e9fbf6344b3e3c8da1d8.jpg_92.jpg',
              desc: '飞走大象'
          },
          {
              id: '007',
              url: 'https://imgs.qunarzz.com/vc/79/80/ee/0bf0779fb0970fbae2ea006388.jpg_92.jpg',
              desc: '挨门脱落'
          },
          {
              id: '008',
              url: 'https://imgs.qunarzz.com/vc/3b/d2/d6/8bb6fa60958cbce87ffea31eb0.jpg_92.jpg',
              desc: '故地重游'
          },
          {
              id: '009',
              url: 'https://imgs.qunarzz.com/tuan/team/2013/c/japan.png',
              desc: '霓虹的灯'
          }
          ]
      }
  },
  computed: {
      pages() {
          const pages = []
          this.iconList.forEach((item, index) => {
              const page = Math.floor(index / 8)
              if (!pages[page]) {
                  pages[page] = []
              }
              pages[page].push(item)
          })
          return pages

      }
  }
}
</script>
<style lang='stylus' scoped>
    @import '~styles/varibles.styl'
    @import '~styles/mixins.styl'
    .icons >>> .swiper-container
        height: 0
        padding-bottom: 50%
    .icon
        position: relative
        overflow: hidden
        width: 25%
        height: 0
        padding-bottom: 25%
        float: left
        .icon-img
            position: absolute 
            box-sizing: border-box
            padding-bottom: .1rem
            top: 0
            left: 0
            right: 0
            bottom: .44rem
            .icon-img-content
                display: block
                height: 100%
                width: 90%
                margin: 0 auto
                border-radius: 70%
        .icon-desc
            display: block
            position: absolute
            left: 0
            right: 0
            bottom: 0
            line-height: .44rem
            height: .44rem
            text-align: center
            color: $darkTextColor
            ellipsis()
</style>
