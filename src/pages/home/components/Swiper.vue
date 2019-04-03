<template>
    <div class="wrapper">
        <swiper :options="swiperOption" v-if="showSwiper">
            <swiper-slide v-for="item of list" :key="item.id">
                <img class="swiper-img" :src="item.imgUrl">
            </swiper-slide>
            <div class="swiper-pagination"  slot="pagination"></div>
        </swiper>
    </div>
</template>
<script>
/* eslint-disable */
export default {
    computed: {
        showSwiper() {
            return this.list.length
        }
    },
    props: {
        list: Array
    },
    data() {
        return{
        swiperOption: {
            pagination: '.swiper-pagination',
            loop: true,
        }
        // swiperList: [{
        //     id: '0001',
        //     imgUrl: 'https://a0.muscache.com/4ea/air/v2/pictures/f049307d-dc45-4795-a183-c5c4910bcf47.jpg?t=r:w1200-h720-sfit,e:fjpg-c90'
        // },
        // {
        //     id: '0002',
        //     imgUrl: 'https://a0.muscache.com/4ea/air/v2/pictures/6784d871-dcc5-4376-b56d-3b83518163fa.jpg?t=r:w1200-h720-sfit,e:fjpg-c90'
        // }]
        
        }
    }
}
</script>
<style lang='stylus' scoped>
.wrapper >>> .swiper-pagination-bullet-active
    background: #fff
.wrapper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 66.73%
    background: #ccc
    box-shadow: 0 .14rem .14rem rgba(0, 0, 0, .15)
    .swiper-img
        width: 100%
</style>
