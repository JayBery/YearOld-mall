<template>
  <div class="page">
    <div class="bottom" route>
        <van-tabbar v-model="active">
            <van-tabbar-item icon="wap-home-o"  replace to="/">首页</van-tabbar-item>
            <van-tabbar-item icon="label-o">分类</van-tabbar-item>
            <van-tabbar-item icon="search">发现</van-tabbar-item>
            <van-tabbar-item icon="shopping-cart-o">购物车</van-tabbar-item>
            <van-tabbar-item icon="contact">我的</van-tabbar-item>
        </van-tabbar>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
import Vue from 'vue';
import { Tabbar, TabbarItem } from 'vant';

Vue.use(Tabbar).use(TabbarItem);

export default {
    name: 'TabbarFooter',
    data() {
        return {
            active: 0,
        }
    },
    components: {

    },
    methods: {

    },
}
</script>

<style scoped lang="stylus">
</style>
