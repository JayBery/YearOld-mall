<template>
  <div class="page">
    <TabbarFooter :active= "message"></TabbarFooter>
  </div>
</template>

<script type="text/ecmascript-6">
import TabbarFooter from '@/components/Tabbar.vue'
import Vue from 'vue';

export default {
  data() {
    return {
      message: 1
    }
  },
  components: {
    TabbarFooter    
  }
}
</script>

<style scoped lang="stylus">
</style>
