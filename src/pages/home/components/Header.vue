<template>
    <div class="header">
        <div class="header-left">
            <span class="iconfont back-icon">&#xe67c;</span>
        </div>
        <div class="header-input">
        <span class="iconfont">&#xe631;</span>
        输入城市/景点/游玩主题
        </div>
        <router-link to="city">
            <div class="header-right">
                {{ this.city }}
                <span class="iconfont arrow-icon">&#xe600;</span>
            </div>
        </router-link>
    </div>
</template>
<script>
import { mapState } from 'vuex'
    export default{
        name: "HomeHeader",
        mounted() {
            console.log( this.$store.state )
        },
        computed: {
            ...mapState(["city"])
        }
    }
</script>
<style lang="stylus" scoped>
    @import  '~@/assets/styles/varibles.styl'
    .header
        display flex
        line-height $headerHeight
        background $bgColor
        color #fff
        .header-left
            width .64rem
            float left
        .header-input
            flex 1
            height .64rem
            background #fff
            margin-top .12rem
            border-radius .1rem
            color #ccc
            line-height .64rem
        .header-right
            min-width 1.04rem
            padding 0 .1rem
            float right
            text-align center
            color #fff
            .arrow-icon
                font-size .24rem
                margin-left -2px
</style>