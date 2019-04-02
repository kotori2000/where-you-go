<template>
    <div>
        <div class="recommend-title">周末去哪儿</div>
        <ul>
            <li class="item border-bottom" v-for="item in recommendList" :key="item.id">
                <div class="item-img-wrapper">
                    <img :src="item.url" class="item-img">
                </div>
                <div class="item-info">
                    <p class="item-title">{{ item.title }}</p>
                    <p class="item-desc">{{ item.desc }}</p>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
/* eslint-disable */
export default {
    name: 'HomeWeekend',
    data () {
        return {
            recommendList: [{
                id: '0001',
                url: 'https://imgs.qunarzz.com/p/tts2/1708/88/842201befbbdad02.jpg_750x440_a1783f2d.jpg',
                title: '黄山一日游',
                desc: '市区酒店免费接送 无购物  天天发团'
            },
            {
                id: '0002',
                url: '//imgs.qunarzz.com/sight/p0/1502/49/49fcca5ceda962d2.water.jpg_640x360_7faf992d.jpg',
                title: '婺源精华一日游',
                desc: '篁岭+江岭+汪口外景+月亮湾'
            },
            {
                id: '0003',
                url: '//imgs.qunarzz.com/sight/p0/1702/13/13c9412b6dd5fab5a3.img.jpg_640x360_1c9ab38c.jpg',
                title: '景区自由行',
                desc: '横店六大景区任选二纯玩一日游'
            },
            {
                id: '0004',
                url: '//imgs.qunarzz.com/sight/p0/1609/94/945ab5b76758703a3.water.jpg_640x360_9ca46f1f.jpg',
                title: '纯玩团❤️门票全含',
                desc: '杭州出发横店影视城一日游 市区免费接'
            },
            {
                id: '0005',
                url: 'https://imgs.qunarzz.com/p/tts6/1808/be/c5cdaf044ca07e02.jpg_750x440_6b585505.jpg',
                title: '双岭赏花一日游送篁岭索道',
                desc: '婺源篁岭+江岭+月亮湾'
            }
            ]
        }
    }
}
</script>
<style lang='stylus' scoped>
@import '~styles/mixins.styl'
.recommend-title
    margin-top: .2rem
    line-height: .8rem
    background: #eeeeee
    text-indent: .2rem
.item-img-wrapper
    overflow: hidden
    height: 0
    padding-bottom: 58.7%
    .item-img
        width: 100%
.item-info
    padding: .1rem
    .item-title
        line-height: .54rem
        font-size: .32rem
        ellipsis()
    .item-desc
        line-height: .4rem
        color: #cccccc
        ellipsis()
</style>
