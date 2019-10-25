<template>
  <div class="page">
      <img src="../images/elevenHaed.png" alt="" width="100%">
      <div class="head">
          <!-- <img src="../images/light.png" alt="" width="100%"> -->
          <van-count-down :time="time" class="jishi">
          <template v-slot="timeData">
            <span class="item">{{ timeData.hours }}</span>天
            <span class="item">{{ timeData.minutes }}</span>时
            <span class="item">{{ timeData.seconds }}</span>分
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
        time: 30 * 60 * 60 * 1000,
    }
  },
  components: {

  },
  methods: {
      success(){
        Toast('领取成功');
      },
      addCart(){
        Toast('已加入购物车');
      }
  },
}
</script>

<style scoped>

.page{
    background: #9a0104;
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

.shopImg{
    font-size: .14rem;
    height: .5rem; 
    color: #333333;
    position: absolute;
}

.shopName{
    font-size: .12rem;
    position: absolute;
}

.price{
    font-size: .14rem;
    color: #fd233c;
    position: absolute;
    height: .4rem;
}

.one .shopImg{
    top: 1.6rem;
    left: .6rem;
}

.one .shopName{
    top: 1.36rem;
    right: .6rem;
}

.one .price{
    top: 1.55rem;
    right: .86rem;
}

.two .shopImg{
    top: 2.8rem;
    left: .6rem;
}

.two .shopName{
    top: 2.64rem;
    right: .76rem;
}

.two .price{
    top: 2.84rem;
    right: .86rem;
}

.three .shopImg{
    top: 3.92rem;
    left: .6rem;
}

.three .shopName{
    top: 3.85rem;
    right: .6rem;
}

.three .price{
    top: 4.05rem;
    right: .86rem;
}

.four .shopImg{
    top: 5.2rem;
    left: .6rem;
}

.four .shopName{
    top: 5rem;
    right: .68rem;
}

.four .price{
    top: 5.2rem;
    right: .86rem;
}

</style>
