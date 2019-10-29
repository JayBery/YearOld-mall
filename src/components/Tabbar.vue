<template>
  <div class="page">
    <div class="bottom" route>
        <van-tabbar v-model="active" >
            <van-tabbar-item icon="wap-home-o" replace to="/home" active="0">首页</van-tabbar-item>
            <van-tabbar-item icon="label-o" replace to="/about" active="1">分类</van-tabbar-item>
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
     props: {
      msg: {
        type: Number,
        default: 0
      }
     },
    data() {
        return {
            active:this.msg  //active接收父组件传来的msg值；
        }
    },
    components: {

    },
    methods: {
        change(active){
            
        }
    }
}
</script>

<style scoped>
.van-tabbar{
    height: .5rem;
}

.van-tabbar >>> .van-tabbar-item .van-tabbar-item__icon{
    font-size: .18rem;
    margin-bottom: .05rem;
}
</style>
