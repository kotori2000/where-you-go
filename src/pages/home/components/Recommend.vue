<template>
    <div>
        <div class="recommend-title">热销推荐</div>
        <ul>
            <li class="item border-bottom" v-for="item in recommendList" :key="item.id">
                <img :src="item.imgUrl" class="item-img">
                <div class="item-info">
                    <p class="item-title">{{ item.title }}</p>
                    <p class="item-desc">{{ item.desc }}</p>
                    <button class="item-button">查看详情</button>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
/* eslint-disable */
export default {
    props: {
        recommendList: Array
    },
    name: 'HomeRecommend',
    data () {
        return {
            // recommendList: [{
            //     id: '0001',
            //     url: 'https://imgs.qunarzz.com/p/tts1/1604/55/236037a432bba9f7.jpg_160x160_99479b6e.jpg',
            //     title: '黄山一日游',
            //     desc: '市区酒店免费接送 无购物  天天发团'
            // },
            // {
            //     id: '0002',
            //     url: 'https://imgs.qunarzz.com/p/tts6/1808/be/c5cdaf044ca07e02.jpg_160x160_5b97cd16.jpg',
            //     title: '婺源精华一日游',
            //     desc: '篁岭+江岭+汪口外景+月亮湾'
            // },
            // {
            //     id: '0003',
            //     url: 'https://imgs.qunarzz.com/p/tts8/1708/54/efff597f9cc34a02.jpg_160x160_37647678.jpg',
            //     title: '景区自由行',
            //     desc: '横店六大景区任选二纯玩一日游'
            // },
            // {
            //     id: '0004',
            //     url: 'https://imgs.qunarzz.com/p/tts0/1809/2d/5f1a62cfede44902.jpg_160x160_dc36a422.jpg',
            //     title: '纯玩团❤️门票全含',
            //     desc: '杭州出发横店影视城一日游 市区免费接'
            // },
            // {
            //     id: '0005',
            //     url: 'https://imgs.qunarzz.com/p/tts7/1903/b4/c135024f291e1502.jpg_160x160_7c22a046.jpg',
            //     title: '双岭赏花一日游送篁岭索道',
            //     desc: '婺源篁岭+江岭+月亮湾'
            // }
            // ]
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
.item
    overflow: hidden
    display: flex
    height: 1.9rem
    .item-img
        width: 1.7rem
        height: 1.7rem
        padding: .1rem
    .item-info
        flex: 1
        padding: .1rem
        min-width: 0
        .item-title
            line-height: .54rem
            font-size: .32rem
            ellipsis()
        .item-desc
            line-height: .4rem
            color: #cccccc
            ellipsis()
        .item-button
            line-height: .44rem
            margin-top: .20rem
            background: #ff9300
            padding: 0 .2rem
            border-radius: .06rem
            color: #fff
</style>
