<template>
  <div class="page">
	<van-swipe :loop="false" indicator-color="#00c7ff">
		<van-swipe-item>
			<img src="../images/bootPage1.jpg" class="bootPage" alt="">
		</van-swipe-item>
		<van-swipe-item>
			<img src="../images/bootPage2.jpg" class="bootPage" alt="">
		</van-swipe-item>
		<van-swipe-item>
			<img src="../images/bootPage3.jpg" class ="bootPage" alt="" @click = "JumpHome">
		</van-swipe-item>
	</van-swipe>
  </div>

</template>

<script type="text/ecmascript-6">
import Vue from 'vue';
import { Swipe, SwipeItem } from 'vant';
import { Lazyload } from 'vant';
Vue.use(Swipe).use(SwipeItem).use(Lazyload);
export default {
  data() {
    return {
    }
  },
  components: {
	  
  },
  methods:{
	  JumpHome(){
		   this.$router.push({path:'/home'})
	  }
  }
}
</script>

<style scoped>
	.page{
		font-size: calc(100vw/3.75);
		width: 100%;

	}
	.bootPage{
		height: 100%;
		width: 100%;
	}
</style>