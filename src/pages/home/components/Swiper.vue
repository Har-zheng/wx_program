<template>
<div class="wrapper">
    <swiper :options="swiperOption" v-if="showSwiper">
        <!-- slides
                        swiperList:[{
                    id: '001',
                    imgUrl: 'http://img1.qunarzz.com/qs/1808/4d/077b11817a69b102.jpg'
                },{
                    id: '002',
                    imgUrl 'http://img1.qunarzz.com/qs/1809/f6/18a4edd3d78d1102.jpg'
                }] -->
        <swiper-slide  v-for=" (item, index) of list" :key="index">
            <img class="swiper-img" :src="item.imgUrl" :key="item.id"/>
        </swiper-slide>
        <!-- Optional controls -->
        <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
    export default{
        name: "HomeSwiper",
        props: {
            list: Array
        },
        data () {
            return {
                swiperOption:{
                    pagination: '.swiper-pagination',
                    loop: true
                }
            }
        },
        computed: {
            showSwiper () {
                return this.list.length
            }
        }
    }
</script>
<style lang="stylus" scoped>
 .wrapper >>> .swiper-pagination-bullet-active
        background #fff !important
.wrapper
    overflow hidden
    width 100%
    height 0
    padding-bottom 30%
    background #eee
    .swiper-img
        width 100%
</style>