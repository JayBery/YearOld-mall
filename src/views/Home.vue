<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <van-button type="default">默认按钮</van-button>
    <TabbarFooter></TabbarFooter>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import TabbarFooter from '@/components/Tabbar.vue'
import Vue from 'vue';
import { Button } from 'vant';

Vue.use(Button);

export default {
  name: 'home',
  components: {
    HelloWorld,
    TabbarFooter
  },
}
</script>
