<template>
	<view class="lo-box-3">
		<image style="width: 33rpx; height: 33rpx; margin-right: 17rpx;" v-if="active" @click="choice()"
			src="/static/login/login-2.png" mode="">
		</image>
		<image style="width: 33rpx; height: 33rpx;margin-right: 17rpx;" @click="choice()" v-else
			src="/static/login/login-3.png" mode=""></image>
		<text class="lo-text-2">已阅读并同意</text>
		<text class="lo-text-2" style="color: rgba(0, 92, 255, 1);">服务协议</text>
		<text class="lo-text-2">和</text>
		<text class="lo-text-2" style="color: rgba(0, 92, 255, 1);"> 隐私保护指引</text>
	</view>
</template>

<script>
	export default {
		props: {
			active: {
				type: Boolean,
				default: true
			}
		},

		data() {
			return {
				isshow: false
			}
		},
		methods: {
			choice() {
				this.isshow = !this.isshow
				this.$emit('update:active', this.isshow);


			},
			navigator_btn(url) {
				uni.navigateTo({
					url: url
				})
			}

		}
	}
</script>

<style scoped lang="scss">
	.lo-box-3 {
		margin-top: 25rpx;
		margin-left: 45rpx;
		display: flex;
		align-items: center;

		.lo-text-2 {
			font-size: 26.16rpx;
			font-weight: 400;
			color: rgba(110, 110, 110, 1);
			// margin-left: 17rpx;
		}
	}
</style>