<template>
    <view class="mine">
        <view style="padding: 20px 0">个人中心</view>
        <view class="btn">
            <nut-button type="primary" @click="handleClick()">后退</nut-button>
        </view>
    </view>
</template>

<script setup lang="ts">
import { navigateBack } from '@tarojs/taro'

const handleClick = () => {
    navigateBack()
}
</script>

<style lang="scss">
.mine {
    text-align: center;
}
</style>
