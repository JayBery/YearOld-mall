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
          <img src="../images/icon1.png" />
          美食
        </van-grid-item>
        <van-grid-item>
          <img src="../images/icon2.png" />
          超市
        </van-grid-item>
        <van-grid-item>
          <img src="../images/icon3.png" />
          生鲜果蔬
        </van-grid-item>
        <van-grid-item>
          <img src="../images/icon4.png" />
          专送
        </van-grid-item>
        <van-grid-item>
          <img src="../images/icon5.png" />
          快餐简餐
        </van-grid-item>
        <van-grid-item>
          <img src="../images/icon6.png" />
          下午茶
        </van-grid-item>
        <van-grid-item>
          <img src="../images/icon7.png" />
          汉堡披萨
        </van-grid-item>
        <van-grid-item>
          <img src="../images/icon8.png" />
          家常菜
        </van-grid-item>
        <van-grid-item>
          <img src="../images/icon9.png" />
          小吃馆
        </van-grid-item>
        <van-grid-item>
          <img src="../images/icon10.png" />
          鲜花蛋糕
        </van-grid-item>
      </van-grid>
    </div>
    <div class="onePart" @click="toOne()">
      <img src="../images/partTwo.png" width="100%">  
    </div>
    <div class="activity clearfix">
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
      <div class="row-card clearfix">
        <div class="left-item">
          <img src="../images/best.png" class="item-pic">
          <div class="name">营养早餐</div>
		  <div class="what what1">"在忙也不要忘记吃早餐"</div>
          <div class="tag">
            <van-tag type="primary" class = "vanTagBg">面包</van-tag>
            <van-tag type="primary" class = "vanTagBg">鸡蛋</van-tag>
            <van-icon name="cart-circle-o" color="#0092eb" />
          </div>
        </div>
        <div class="right-item">
          <img src="../images/bestTwo.png" class="item-pic">
          <div class="name">海鲜拉面</div> 
		  <div class="what what1">"在忙也不要忘记吃早餐"</div>
          <div class="tag">
            <van-tag type="primary" class = "vanTagBg">拉面</van-tag>
            <van-tag type="primary" class = "vanTagBg">鸭蛋</van-tag>
            <van-icon name="cart-circle-o" color="#0092eb" />
          </div>
        </div>
      </div>
    </div>
    <div class="tab">
      <van-tabs v-model="active" color="#006be5">
        <van-tab title="热门推荐">
          <div class="allThing">
            <div class="tingRow clearfix">
              <div class="left">
                <div class="imgDiv">
                <img src="../images/shop.png" width="80%">
                </div>
                <div class="theName">正宗新鲜土鸡蛋/40枚</div>
                <div class="what">"蛋黄饱满,富有弹性"</div>
                <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
              </div>
              <div class="right">
                <div class="imgDiv">
                <img src="../images/shopTwo.png" width="80%">
                </div>
                <div class="theName">正宗新鲜土鸡蛋/40枚</div>
                <div class="what">"蛋黄饱满,富有弹性"</div>
                <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
              </div>
            </div>
          </div>
          <div class="allThing">
            <div class="tingRow clearfix">
              <div class="left">
                <div class="imgDiv">
                <img src="../images/shopThree.png" width="80%">
                </div>
                <div class="theName">正宗新鲜土鸡蛋/40枚</div>
                <div class="what">"蛋黄饱满,富有弹性"</div>
                <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
              </div>
              <div class="right">
                <div class="imgDiv">
                <img src="../images/shopFour.png" width="80%">
                </div>
                <div class="theName">正宗新鲜土鸡蛋/40枚</div>
                <div class="what">"蛋黄饱满,富有弹性"</div>
                <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
              </div>
            </div>
          </div>
        </van-tab>
        <van-tab title="水果">
          <div class="allThing">
            <div class="tingRow clearfix">
              <div class="left">
                <div class="imgDiv">
                <img src="../images/shopThree.png" width="80%">
                </div>
                <div class="theName">新鲜樱桃/斤</div>
                <div class="what">"蛋黄饱满,富有弹性"</div>
                <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
              </div>
              <div class="right">
                <div class="imgDiv">
                <img src="../images/shopgrape.jpg" width="80%">
                </div>
                <div class="theName">新鲜葡萄/斤</div>
                <div class="what">"蛋黄饱满,富有弹性"</div>
                <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
              </div>
            </div>
          </div>
		  <div class="allThing">
		    <div class="tingRow clearfix">
		      <div class="left">
		        <div class="imgDiv">
		        <img src="../images/shopMangosteen.jpg" width="80%">
		        </div>
		        <div class="theName">新鲜山竹/斤</div>
		        <div class="what">"蛋黄饱满,富有弹性"</div>
		        <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
		      </div>
		      <div class="right">
		        <div class="imgDiv">
		        <img src="../images/shopApple.jpg" width="80%">
		        </div>
		        <div class="theName">新鲜苹果/斤</div>
		        <div class="what">"蛋黄饱满,富有弹性"</div>
		        <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
		      </div>
		    </div>
		  </div>
        </van-tab>
        <van-tab title="蔬菜">
			<div class="allThing">
			  <div class="tingRow clearfix">
			    <div class="left">
			      <div class="imgDiv">
			      <img src="../images/shopVegetables.jpg" width="80%">
			      </div>
			      <div class="theName">新鲜蔬菜/斤</div>
			      <div class="what">"蛋黄饱满,富有弹性"</div>
			      <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
			    </div>
			    <div class="right">
			      <div class="imgDiv">
			      <img src="../images/shopVegetables1.jpg" width="80%">
			      </div>
			      <div class="theName">新鲜蔬菜/斤</div>
			      <div class="what">"蛋黄饱满,富有弹性"</div>
			      <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
			    </div>
			  </div>
			</div>
			<div class="allThing">
			  <div class="tingRow clearfix">
			    <div class="left">
			      <div class="imgDiv">
			      <img src="../images/shopVegetables.jpg" width="80%">
			      </div>
			      <div class="theName">新鲜蔬菜/斤</div>
			      <div class="what">"蛋黄饱满,富有弹性"</div>
			      <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
			    </div>
			    <div class="right">
			      <div class="imgDiv">
			      <img src="../images/shopVegetables1.jpg" width="80%">
			      </div>
			      <div class="theName">新鲜蔬菜/斤</div>
			      <div class="what">"蛋黄饱满,富有弹性"</div>
			      <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
			    </div>
			  </div>
			</div>
		</van-tab>
        <van-tab title="肉禽蛋类">
			<div class="allThing">
			  <div class="tingRow clearfix">
			    <div class="left">
			      <div class="imgDiv">
			      <img src="../images/shopChicken.jpg" width="80%">
			      </div>
			      <div class="theName">清远土鸡/斤</div>
			      <div class="what">"蛋黄饱满,富有弹性"</div>
			      <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
			    </div>
			    <div class="right">
			      <div class="imgDiv">
			      <img src="../images/shopDuck.png" width="80%">
			      </div>
			      <div class="theName">陕西走地鸭/斤</div>
			      <div class="what">"蛋黄饱满,富有弹性"</div>
			      <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
			    </div>
			  </div>
			</div>
			<div class="allThing">
			  <div class="tingRow clearfix">
			    <div class="left">
			      <div class="imgDiv">
			      <img src="../images/shopEgg.jpg" width="80%">
			      </div>
			      <div class="theName">有机优质蛋/斤</div>
			      <div class="what">"蛋黄饱满,富有弹性"</div>
			      <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
			    </div>
			    <div class="right">
			      <div class="imgDiv">
			      <img src="../images/shopBeef.jpg" width="80%">
			      </div>
			      <div class="theName">新鲜牛肉/斤</div>
			      <div class="what">"蛋黄饱满,富有弹性"</div>
			      <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
			    </div>
			  </div>
			</div>
		</van-tab>
        <van-tab title="水产海鲜">
			<div class="allThing">
			  <div class="tingRow clearfix">
			    <div class="left">
			      <div class="imgDiv">
			      <img src="../images/shopLobster.jpg" width="80%">
			      </div>
			      <div class="theName">美国波士顿龙虾/只</div>
			      <div class="what">"蛋黄饱满,富有弹性"</div>
			      <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
			    </div>
			    <div class="right">
			      <div class="imgDiv">
			      <img src="../images/shopCrab.jpg" width="80%">
			      </div>
			      <div class="theName">无为县大闸蟹/斤</div>
			      <div class="what">"蛋黄饱满,富有弹性"</div>
			      <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
			    </div>
			  </div>
			</div>
			<div class="allThing">
			  <div class="tingRow clearfix">
			    <div class="left">
			      <div class="imgDiv">
			      <img src="../images/shopAbalone.jpg" width="80%">
			      </div>
			      <div class="theName">大连鲍鱼/只</div>
			      <div class="what">"蛋黄饱满,富有弹性"</div>
			      <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
			    </div>
			    <div class="right">
			      <div class="imgDiv">
			      <img src="../images/shopHairtail.jpg" width="80%">
			      </div>
			      <div class="theName">深海带鱼/斤</div>
			      <div class="what">"蛋黄饱满,富有弹性"</div>
			      <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
			    </div>
			  </div>
			</div>
		</van-tab>
        <van-tab title="粮油调品">
			<div class="allThing">
			  <div class="tingRow clearfix">
			    <div class="left">
			      <div class="imgDiv">
			      <img src="../images/shopThaiRice.jpg" width="80%">
			      </div>
			      <div class="theName">泰国香米/袋</div>
			      <div class="what">"蛋黄饱满,富有弹性"</div>
			      <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
			    </div>
			    <div class="right">
			      <div class="imgDiv">
			      <img src="../images/shopNortheastRice.jpg" width="80%">
			      </div>
			      <div class="theName">东北大米/袋</div>
			      <div class="what">"蛋黄饱满,富有弹性"</div>
			      <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
			    </div>
			  </div>
			</div>
			<div class="allThing">
			  <div class="tingRow clearfix">
			    <div class="left">
			      <div class="imgDiv">
			      <img src="../images/shopJLYOil.jpeg" width="80%">
			      </div>
			      <div class="theName">金龙鱼玉米油/桶</div>
			      <div class="what">"蛋黄饱满,富有弹性"</div>
			      <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
			    </div>
			    <div class="right">
			      <div class="imgDiv">
			      <img src="../images/shopOliveoil.jpg" width="80%">
			      </div>
			      <div class="theName">橄榄油/桶</div>
			      <div class="what">"蛋黄饱满,富有弹性"</div>
			      <div class="price">32.99<van-icon name="cart-circle-o" color="#0092eb" /></div>
			    </div>
			  </div>
			</div>
		</van-tab>
      </van-tabs>
    </div>
    <TabbarFooter :msg= "message"></TabbarFooter>
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
import { Tab, Tabs } from 'vant';

Vue.use(Tab).use(Tabs)
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
      message: 0,
      value: "",
      time: 30 * 60 * 60 * 1000,
      active: 0
    }
  },
  components: {
    HelloWorld,
    TabbarFooter
  },
   methods: {
    toOne(){
      this.$router.push({path:'/DoubleEleven'})
    }
  }
}
</script>

<style scoped>

.page{
  margin-bottom: .6rem
}
.headGPS{
  margin-top: .1rem;
  font-weight:600;
  font-size: .16rem;
}

.headGPS .van-icon-location{
  font-size: .15rem;
}

.headGPS .van-icon-arrow-down{
  font-size: .15rem;
}

.swiper {
  width: 92%;
  margin: 0 auto;
}

.swiper .van-swipe{
  width: 100%;
  height: 100%;
}

.swiper img {
  width: 100%;
  border-radius: .18em; 
}

.van-grid{
  font-size: .1rem;
  color: #595959;
}

.van-grid img{
  height: .49rem;
  border-radius:10%;
  margin-bottom: .06rem;
}

.onePart{
  margin: 0 auto;
}

.activity{
  margin: 0 auto;
  width: 96%;
  font-size: .16rem;
}
.item {
  display: inline-block;
  width: .2rem;
  color: #fff;
  font-size: .12rem;
  text-align: center;
  background-color: #c82828;
  border-radius: .02rem;
}


.act-left{
  border: 1px solid #cccccc;
  width: 48%;
  max-height: 1.6rem;
  float: left;
  overflow: hidden;
}

.act-left .text{
  color: #595959;
  margin-right: .1rem;
}

.act-left .van-count-down{
  color: #333333;
  margin: .08rem 0 .1rem .01rem;
  font-size: .16rem;
}

.act-rightTop{
  width: 49%;
  max-height: .79rem;
  float: right;
  border: 1px solid #cccccc;
  text-align: left;
  overflow: hidden;
}

.act-rightTop span{
  margin-left: .1rem;
}

.act-rightTop img{
  width: 63%;
  float: right;
}

.todayBest{
  /* height: 13rem; */
  margin-top: .1rem
}

.todayBest .tb-title{
  text-align: left;
  color: #006be5;
  font-size: .2rem;
  font-weight: 600;
  margin: 0 .1rem .1rem .1rem;
}

.todayBest .tb-title .more{
  float: right;
  color: #b3b3b3;
  font-size: .14rem;
  font-weight: 100;
  line-height: .3rem;
}

.left-item{
  font-size: .18rem;
  /* height: 11rem; */
  width: 46%;
  border: 1px solid #dadada;
  margin: .02rem 0 0 .1rem;
  border-radius: .1rem;
  box-shadow: 2px 4px 6px #dadada;
  float: left;
}

.left-item .item-pic{
  width: 94%;
  margin: .2rem 0 0 0;
}

.left-item .name{
  text-align: left;
  margin: .06rem 0 .06rem .1rem;
  font-size: .16rem;
  color: #333;
  font-weight: 600
}

.left-item .tag{
  text-align: left;
  margin-left: .1rem;
  margin-top: .08rem;
}

.left-item .tag .van-tag{
  margin-right: .1rem;
  color: #1f1e6a;
}

.left-item .tag .van-icon{
  float: right;
  font-size: .3rem;
  margin: 0 .1rem .1rem 0;
}

.right-item{
  font-size: .18rem;
  /* height: 11rem; */
  width: 46%;
  border: 1px solid #dadada;
  margin: .02rem .1rem 0 0;
  border-radius: .1rem;
  box-shadow: 2px 4px 6px #dadada;
  float: right;
}

.right-item .item-pic{
  width: 94%;
  margin: .2rem 0 0 0;
}

.right-item .name{
  text-align: left;
  margin: .06rem 0 .06rem .1rem;
  font-size: .16rem;
  color: #333333;
  font-weight: 600
}

.right-item .tag{
  text-align: left;
  margin-left: .1rem;
  margin-top: .08rem;
}

.right-item .tag .van-tag{
  margin-right: .1rem;
  color: #1f1e6a;
}

.right-item .tag .van-icon{
  float: right;
  font-size: .3rem;
  margin: 0 .1rem .1rem 0;
}

.tab{
  margin-top: .06rem;
}

.clearfix::after {
    content:"";
    display:table;
    clear: both;
}

.allThing{
  background: #e6e6e6;
}

.left{
  width: 50%;
  background: #fff;
  float: left;
}

.right{
  width: 50%;
  background: #fff;
  float: right;
}

.theName{
  text-align: left;
  padding-left: .1rem;
  padding-bottom: .1rem;
  font-size: .15rem;
}

.what{
  text-align: left;
  padding-left: .1rem;
  color: #808080;
  font-size: .12rem;
}

.what1{
  padding-left: 0.1rem;
}

.price{
  text-align: left;
  color: #ff0000;
  padding-left: .1rem;
  padding-top: .1rem;
  font-size: .18rem;
}

.price .van-icon{
  float: right;
  font-size: .3rem;
  padding-left: -.1rem;
  margin-right: .1rem;
  /* margin-bottom: .06rem; */
}
.imgDiv{
  justify-content: center;
  display: flex;
  align-items: center;
  height: 2rem;
}

.vanTagBg{
	background-color: #ebf1fd;
}

.tag .van-tag{
  font-size: .1rem;
}

.tab >>> .van-tab{
  font-size: .14rem;
}

</style>
