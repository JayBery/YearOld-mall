<template>
<div class="page">
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <!-- <van-button type="default">默认按钮</van-button> -->
    <div class="headGPS">
      <van-icon name="location" color="#0e9afc" />
      深圳技师学院
      <van-icon name="arrow-down" />
    </div>
    <div>
      <van-search
        v-model="value"
        placeholder="请输入搜索关键词"
        shape="round"
        input-align="center"
      >
      </van-search>
    </div>
    <div class="swiper">
      <van-swipe :autoplay="5000" indicator-color="#fff">
        <van-swipe-item>
          <img src="../images/banner.png">
        </van-swipe-item>
        <van-swipe-item>
          <img src="../images/banner.png">
        </van-swipe-item>
        <van-swipe-item>
          <img src="../images/banner.png">
        </van-swipe-item>
      </van-swipe>
    </div>
    <div>
      <van-grid :column-num="5" :border="false">
        <!-- <van-grid-item
          v-for="value in 10"
          :key="value"
          icon="photo-o"
          text="文字"
        /> -->
        <van-grid-item>
          <img src="https://p1.meituan.net/jungle/8b5e1702d4145ccf058ba5fb31008c5310912.png" />
          美食
        </van-grid-item>
        <van-grid-item>
          <img src="https://p0.meituan.net/jungle/45ff2f098a20a77122bff8385192f0ec10547.png" />
          超市
        </van-grid-item>
        <van-grid-item>
          <img src="https://p1.meituan.net/jungle/12a9834827909fa55f54bce96e67470711250.png" />
          生鲜果蔬
        </van-grid-item>
        <van-grid-item>
          <img src="https://p1.meituan.net/jungle/da9181f93dd2e11c5d74cf685470408f10016.png" />
          专送
        </van-grid-item>
        <van-grid-item>
          <img src="https://p1.meituan.net/jungle/83bfbcf07221cb1ccbcd9114e81ec7ac9209.png" />
          快餐简餐
        </van-grid-item>
        <van-grid-item>
          <img src="https://p1.meituan.net/jungle/a2a306c5467aba7fac8d7410d161f8db9364.png" />
          下午茶
        </van-grid-item>
        <van-grid-item>
          <img src="https://p0.meituan.net/jungle/58b60a312cf86f3a3afc4c96ff0e53438774.png" />
          汉堡披萨
        </van-grid-item>
        <van-grid-item>
          <img src="https://p0.meituan.net/jungle/2eee7747fd143249b100b9fa5ee5e31d9873.png" />
          家常菜
        </van-grid-item>
        <van-grid-item>
          <img src="https://p0.meituan.net/jungle/2ec76f8f4f21a4ec163adc7fccfa1a399428.png" />
          小吃馆
        </van-grid-item>
        <van-grid-item>
          <img src="https://p1.meituan.net/jungle/dfd03fd91f640682c16179ba85837f739679.png" />
          鲜花蛋糕
        </van-grid-item>
      </van-grid>
    </div>
    <div class="onePart">
      <img src="../images/partTwo.png" width="100%">  
    </div>
    <div class="activity">
      <div class="act-left">
        <van-count-down :time="time">
          <template v-slot="timeData">
            <span class="text">限时抢购</span>
            <span class="item">{{ timeData.hours }}</span>:
            <span class="item">{{ timeData.minutes }}</span>:
            <span class="item">{{ timeData.seconds }}</span>
          </template>
        </van-count-down>
        <!-- <div class="pic"><img src="../images/partThree.png" width="100%" height="100%" style="float:right;overflow:hidden"></div> -->
        <img src="../images/partThree.png" width="100%" style="float:right">
      </div>
      <div class="act-rightTop">
        <span>天天拼团</span>
        <img src="../images/partFour.png">
      </div>
      <div class="act-rightTop">
        <span>每日好货</span>
        <img src="../images/partSix.png">
      </div>
    </div>
    <div class="todayBest">
      <div class="tb-title">今日最佳<span class="more">查看更多<van-icon name="arrow"  color="#b3b3b3" /></span></div>
      <div class="row-card">
        <div class="left-item">
          <img src="../images/best.png" class="item-pic">
          <div class="name">营养早餐</div> 
          <div class="tag">
            <van-tag type="primary">面包</van-tag>
            <van-tag type="primary">鸡蛋</van-tag>
            <van-icon name="cart-circle-o" color="#0092eb" />
          </div>
        </div>
        <div class="right-item">
          <img src="../images/bestTwo.png" class="item-pic">
          <div class="name">海鲜拉面</div> 
          <div class="tag">
            <van-tag type="primary">拉面</van-tag>
            <van-tag type="primary">鸭蛋</van-tag>
            <van-icon name="cart-circle-o" color="#0092eb" />
          </div>
        </div>
      </div>
    </div>
    <TabbarFooter></TabbarFooter>
  </div>
</div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import TabbarFooter from '@/components/Tabbar.vue'
import Vue from 'vue';
import { Icon } from 'vant';
import { Button } from 'vant';
import { Search } from 'vant';
import { Swipe, SwipeItem } from 'vant';
import { Grid, GridItem } from 'vant';
import { CountDown } from 'vant';
import { Tag } from 'vant';

Vue.use(Tag);
Vue.use(CountDown);
Vue.use(Grid).use(GridItem);
Vue.use(Swipe).use(SwipeItem);
Vue.use(Icon);
Vue.use(Button);
Vue.use(Search);

export default {
  name: 'home',
  data() {
    return {
      value: "",
      time: 30 * 60 * 60 * 1000
    }
  },
  components: {
    HelloWorld,
    TabbarFooter
  },
   methods: {
    
  }
}
</script>

<style>

.page{
  margin-bottom: 3.5rem
}
.headGPS{
  margin: 1rem 0 .2rem 0;
  font-weight:600;
}

.headGPS .van-icon-location{
  font-size: .9rem;
}

.headGPS .van-icon-arrow-down{
  font-size: .6rem;
}



.swiper {
  width: 92%;
  margin: .3rem 4% 1rem 4%;
  /* height: 12rem; */
}

.swiper .van-swipe{
  width: 100%;
  height: 100%;
  border-radius: 1rem;
}
.swiper img {
  width: 100%;
  height: 100%;
  pointer-events: none;
}
.swiper .custom-indicator {
  position: absolute;
  right: 5px;
  bottom: 5px;
  padding: 2px 5px;
  font-size: 12px;
  color: #fff;
  background: #fff;
}

.van-grid{
  font-size: .12rem;
  color: #595959;
}

.van-grid img{
  height: 2.8rem;
  border-radius:2.8rem;
  margin-bottom: .3rem;
}

.onePart{
  margin: 0 auto;
}

.activity{
  margin: 0 auto;
  width: 96%;
  height: 11rem;
}
.item {
  display: inline-block;
  width: 22px;
  /* margin-right: 5px; */
  color: #fff;
  font-size: 12px;
  text-align: center;
  background-color: #c82828;
  border-radius: 4px;
}

.act-left{
  border: 1px solid #cccccc;
  width: 48%;
  height: 10rem;
  float: left;
  overflow: hidden;
}

.act-left .text{
  color: #595959;
  margin-right: .5rem;
}

.act-left .van-count-down{
  color: #333333;
  float: left;
  margin: .1rem 0 .1rem .5rem
}

.van-count-down .pic{
  margin-top: .9rem
}

.act-rightTop{
  width: 49%;
  height: 4.95rem;
  float: right;
  border: 1px solid #cccccc;
  text-align: left;
  overflow: hidden;
}

.act-rightTop span{
  margin-left: .4rem;
  /* display: block; */
}

.act-rightTop img{
  width: 63%;
  float: right;
}

.todayBest{
  height: 13rem;
}

.todayBest .tb-title{
  text-align: left;
  color: #006be5;
  font-size: 1.2rem;
  font-weight: 600;
  margin: 0 .4rem .2rem .4rem;
}

.todayBest .tb-title .more{
  float: right;
  color: #b3b3b3;
  font-size: .8rem;
  font-weight: 100;
  line-height: 1.6rem;
}

.left-item{
  height: 11rem;
  width: 46%;
  border: 1px solid #dadada;
  margin: .3rem 0 0 .6rem;
  border-radius: .6rem;
  box-shadow: 2px 4px 6px #dadada;
  float: left;
}

.left-item .item-pic{
  width: 94%;
  margin: .8rem 0 0 0;
}

.left-item .name{
  text-align: left;
  margin: .5rem 0 .5rem .3rem;
}

.left-item .tag{
  text-align: left;
  margin-left: .3rem;
}

.left-item .tag .van-tag{
  margin-right: .3rem;
}

.left-item .tag .van-icon{
  float: right;
  font-size: 2.1rem;
  margin: -1rem .6rem 0 0
}

.right-item{
  height: 11rem;
  width: 46%;
  border: 1px solid #dadada;
  margin: .3rem .3rem 0 0;
  border-radius: .6rem;
  box-shadow: 2px 4px 6px #dadada;
  float: right;
}

.right-item .item-pic{
  width: 94%;
  margin: .8rem 0 0 0;
}

.right-item .name{
  text-align: left;
  margin: .5rem 0 .5rem .3rem;
}

.right-item .tag{
  text-align: left;
  margin-left: .3rem;
}

.right-item .tag .van-tag{
  margin-right: .3rem;
}

.right-item .tag .van-icon{
  float: right;
  font-size: 2.1rem;
  margin: -1rem .6rem 0 0
}
</style>
