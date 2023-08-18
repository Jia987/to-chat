<template>
  <view>
    <view class="mask" v-show="showDialog" @click="hideDialog"></view>
    <view class="dialog" v-show="showDialog">
      <slot></slot>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      showDialog: false // 控制弹框显示与隐藏的变量
    };
  },
  methods: {
    show() {
      this.showDialog = true;
    },
    hide() {
      this.showDialog = false;
    },
    hideDialog() {
      // 点击遮盖层时隐藏弹框
      this.hide();
    }
  }
};
</script>

<style>
.mask {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5); /* 遮盖层的颜色和透明度 */
  z-index: 9999; /* 设置遮盖层的层级 */
}

.dialog {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: #fff;
  z-index: 10000; /* 设置弹框的层级 */
}
</style>