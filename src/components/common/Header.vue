<template>
  <div>
    <van-nav-bar title="首页" left-text="返回" @click-left="onClickLeft"
    @click-right="onClickRight" left-arrow>
      <van-icon v-if="false" name="search" slot="right" />
    </van-nav-bar>
  </div>
</template>
<script>
import { Toast } from 'vant';
export default {
  methods: {
    onClickLeft() {
      Toast('返回');
    },
    onClickRight() {
      Toast('按钮');
    }
  },
}
</script>