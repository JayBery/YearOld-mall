<template>
  <div class="page">
      <img src="../images/elevenHaed.png" alt="" width="100%">
      <div class="goIndex" @click="goIndex()">返回首页</div>
      <div class="head">
          <!-- <img src="../images/light.png" alt="" width="100%"> -->
          <van-count-down :time="time" class="jishi">
          <template v-slot="timeData">
            <span class="item">{{ timeData.days }}</span>天
            <span class="item">{{ timeData.hours }}</span>时
            <span class="item">{{ timeData.minutes }}</span>分
            <span class="item">{{ timeData.seconds }}</span>秒
          </template>
        </van-count-down>
      </div>
      <div class="quanAll">
          <img src="../images/quan1.png" @click="success()">
          <img src="../images/quan2.png" @click="success()">
          <img src="../images/quan3.png" @click="success()">
      </div>
      <div class="showAll">
            <div class="one">
              <img class="shopImg" src="../images/shopShowOne.png">
              <div class="shopName">红富士苹果/10KG</div>
              <div class="price" @click="addCart()">￥50.00</div>
            </div>
            <div class="two">
              <img class="shopImg" src="../images/shopShowTwo.png">
              <div class="shopName">小米蕉/5KG</div>
              <div class="price" @click="addCart()">￥50.00</div>
            </div>
            <div class="three">
              <img class="shopImg" src="../images/shopShowThree.png">
              <div class="shopName">绿心猕猴桃/5KG</div>
              <div class="price" @click="addCart()">￥50.00</div>
            </div>
            <div class="four">
              <img class="shopImg" src="../images/shopShowFour.png">
              <div class="shopName">丹棱桔橙/5KG</div>
              <div class="price" @click="addCart()">￥50.00</div>
            </div>
      </div>
      <div class="lookMore">
          <img src="../images/lookMore.png">
      </div>
      <div class="qiangShow">
            <div class="one">
              <div class="shopName">清扬洗发水</div>
              <img class="shopImg" src="../images/hot1.png">
              <div class="price" @click="addCart()">￥159</div>
            </div>
            <div class="two">
              <div class="shopName">蓝月亮洗衣液</div>
              <img class="shopImg" src="../images/hot2.png">
              <div class="price" @click="addCart()">￥119</div>
            </div>
            <div class="three">
              <div class="shopName">曼秀雷敦洗面奶</div>
              <img class="shopImg" src="../images/hot3.png">
              <div class="price" @click="addCart()">￥29</div>
            </div>
            <div class="four">
              <div class="shopName">坚果大礼包</div>
              <img class="shopImg" src="../images/hot4.png">
              <div class="price" @click="addCart()">￥89</div>
            </div>
            <div class="five">
              <div class="shopName">乐事薯片</div>
              <img class="shopImg" src="../images/hot5.png">
              <div class="price" @click="addCart()">￥36</div>
            </div>
            <div class="six">
              <div class="shopName">小老板紫菜卷</div>
              <img class="shopImg" src="../images/hot6.png">
              <div class="price" @click="addCart()">￥59</div>
            </div>
      </div>
      <div class="lookMore2">
          <img src="../images/lookMore.png">
      </div>
      <div class="bottom">
          <img src="../images/bottom.png" width="100%">
      </div>
  </div>
</template>

<script type="text/ecmascript-6">
import { CountDown } from 'vant';
import Vue from 'vue';
import { Toast } from 'vant';

Vue.use(Toast);
Vue.use(CountDown);
export default {
  data() {
    return {
        time: 0,
    }
  },
  created:function(){
    var timestamp = (new Date()).getTime();
    this.interval(timestamp,1573401600000)
  },
  components: {

  },
  methods: {
      success(){
        Toast('领取成功');
      },
      addCart(){
        Toast('已加入购物车');
      },
      goIndex(){
          this.$router.push({path: '/Home'})
      },
      interval(faultDate,completeTime){
        var stime = Date.parse(new Date(faultDate));
        var etime = Date.parse(new Date(completeTime));
        var usedTime = etime - stime;  //两个时间戳相差的毫秒数
        this.time = usedTime;
      }
  },
}
</script>

<style scoped>
.page{
    background: #8c0208;
}

.goIndex{
    font-size: .16rem;
    color: #ffffff;
    position: relative;
    z-index: 1;
    top: -.3rem;
}

.head{
    position: relative;
    background-image: url(../images/light.png);
    background-size: 100% 100%;
    background-repeat: no-repeat;
    margin:0 auto;
    margin-top: -.3rem;
}
.head::after {
    content: "";
    display: block;
    /*这里的padding =  height / width*/
    padding:10%;
}

.jishi{
    position:absolute;
    width: 100%;
    bottom: 10%;
    color: #6d000a;
    font-size: .16rem;
}

.item {
  display: inline-block;
  width: .22rem;
  margin-right: .05rem;
  color: #fff;
  font-size: .14rem;
  text-align: center;
  /* background-color: #1989fa; */
}

.quanAll{
    width: 100%;
    margin-top: -.36rem;
}

.quanAll img{
    width: 30%;
}

.showAll{
    position: relative;
    background-image: url(../images/shopShow.png);
    background-size: 100% 100%;
    background-repeat: no-repeat;
    margin:0 auto;
}

.showAll::after {
    content: "";
    display: block;
    /*这里的padding =  height / width*/
    padding:80%;
    padding-right: 0;
}

.showAll .shopImg{
    font-size: .14rem;
    height: .5rem; 
    color: #333333;
    position: absolute;
}

.showAll .shopName{
    font-size: .12rem;
    position: absolute;
}

.showAll .price{
    font-size: .14rem;
    color: #fd233c;
    position: absolute;
    height: .4rem;
}

.showAll .one .shopImg{
    top: 1.6rem;
    left: .6rem;
}

.showAll .one .shopName{
    top: 1.36rem;
    right: .6rem;
}

.showAll .one .price{
    top: 1.55rem;
    right: .86rem;
}

.showAll .two .shopImg{
    top: 2.8rem;
    left: .6rem;
}

.showAll .two .shopName{
    top: 2.64rem;
    right: .76rem;
}

.showAll .two .price{
    top: 2.81rem;
    right: .86rem;
}

.showAll .three .shopImg{
    top: 3.92rem;
    left: .6rem;
}

.showAll .three .shopName{
    top: 3.85rem;
    right: .6rem;
}

.showAll .three .price{
    top: 4.04rem;
    right: .86rem;
}

.showAll .four .shopImg{
    top: 5.2rem;
    left: .6rem;
}

.showAll .four .shopName{
    top: 5rem;
    right: .68rem;
}

.showAll .four .price{
    top: 5.2rem;
    right: .86rem;
}


.lookMore{
    margin-top: -.62rem;
}
.lookMore2{
    margin-top: -.75rem;
}

.lookMore img{
    width: 88%;
}
.lookMore2 img{
    width: 88%;
}

.qiangShow{
    position: relative;
    background-image: url(../images/qiangShow.png);
    background-size: 100% 100%;
    background-repeat: no-repeat;
    margin:0 auto;
}

.qiangShow::after {
    content: "";
    display: block;
    /*这里的padding =  height / width*/
    padding:58%;
    padding-right: 0;
}


.qiangShow .shopImg{
    font-size: .14rem;
    height: .8rem; 
    position: absolute;
}

.qiangShow .shopName{
    font-size: .12rem;
    position: absolute;
    color: #ffffff;
}

.qiangShow .price{
    font-size: .14rem;
    color: #fefefe;
    position: absolute;
    width: 1rem;
    text-align: left;
}

.qiangShow .one .shopName{
    top: .17rem;
    left: .65rem;
}

.qiangShow .one .shopImg{
    top: .85rem;
    left: .4rem;
}

.qiangShow .one .price{
    top: 1.78rem;
    left: .24rem;
}

.qiangShow .two .shopName{
    top: .17rem;
    left: 1.5rem;
}

.qiangShow .two .shopImg{
    top: .85rem;
    left: 1.4rem;
}

.qiangShow .two .price{
    top: 1.78rem;
    left: 1.36rem;
}

.qiangShow .three .shopName{
    top: .17rem;
    left: 2.37rem;
}

.qiangShow .three .shopImg{
    top: .85rem;
    left: 2.5rem;
}

.qiangShow .three .price{
    top: 1.78rem;
    left: 2.5rem;
}

.qiangShow .four .shopName{
    top: 2.34rem;
    left: .6rem;
}

.qiangShow .four .shopImg{
    top: 3rem;
    left: .4rem;
}

.qiangShow .four .price{
    top: 3.95rem;
    left: .28rem;
}

.qiangShow .five .shopName{
    top: 2.34rem;
    left: 1.6rem;
}

.qiangShow .five .shopImg{
    top: 3rem;
    left: 1.48rem;
}

.qiangShow .five .price{
    top: 3.95rem;
    left: 1.38rem;
}

.qiangShow .six .shopName{
    top: 2.34rem;
    left: 2.44rem;
}

.qiangShow .six .shopImg{
    top: 3rem;
    left: 2.56rem;
}

.qiangShow .six .price{
    top: 3.95rem;
    left: 2.49rem;
}
.bottom{
    display: flex;
}
</style>
