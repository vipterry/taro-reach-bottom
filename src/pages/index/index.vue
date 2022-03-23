<template>
  <view class="index">
    <view>往下拉，然后点击个人中心，再然后点击后退，循环几次，useReachBottom就会触发执行几次！</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view>往下拉</view>
    <view class="btn">
      <!-- <nut-button type="primary" @click="handleClick('text', msg2, true)">点我</nut-button> -->
      <nut-button type="primary" @click="handleMine()">个人中心</nut-button>
    </view>
    <nut-toast :msg="msg" v-model:visible="show" :type="type" :cover="cover" />
  </view>
</template>

<script>
import { reactive, toRefs } from 'vue';
import { navigateTo, usePullDownRefresh, useReachBottom, stopPullDownRefresh } from '@tarojs/taro'
export default {
  name: 'Index',
  components: {
    
  },
  setup(){
    const state = reactive({
      msg: '欢迎使用 NutUI3.0 开发小程序',
      msg2: '你成功了～',
      type: 'text',
      show: false,
      cover: false
    });

    const handleClick = (type, msg, cover = false) => {
      state.show = true;
      state.msg2 = msg;
      state.type = type;
      state.cover = cover;
    };

    let index = 0
    useReachBottom(() => {
        console.log('useReachBottom...', index++)
    })

    const handleMine = () => {
      navigateTo({
          url: '/pages/mine/index'
      }).then(console.log, console.error)
    }

    return {
      ...toRefs(state),
      handleClick,
      handleMine
    }
  }
}
</script>

<style lang="scss">
.index {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>
