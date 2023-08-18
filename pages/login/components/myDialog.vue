<template>
	<div class="my-dialog" v-if="visible">
		<div class="dialog-content">
			<text class="di-text">密码不一致</text>
			<view class="di-box-1">
				<text>密码不一致，请重新输入</text>
			</view>
			<!-- 	<button @click="closeDialog">关闭</button> -->
			<view class="di-box">
				<text>确定</text>
			</view>
		</div>
	</div>
</template>

<script>
	export default {
		props: {
			visible: Boolean
		},
		methods: {
			closeDialog() {
				this.$emit('close');
			}
		}
	};
</script>

<style scoped>
	.my-dialog {
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background-color: rgba(0, 0, 0, 0.7);
		display: flex;
		align-items: center;
		justify-content: center;
		z-index: 9999;
	}

	.dialog-content {
		background-color: white;
		width: 555rpx;
		height: 375rpx;
		border-radius: 48rpx;
		text-align: center;
		display: flex;
		flex-direction: column;
		/* 垂直排列子元素 */
		/* align-items: center; */
		/* 可根据需要调整对齐方式 */

		.di-text {
			margin-top: 47rpx;
			font-size: 41.86rpx;
			font-weight: 400;
		}

		.di-box-1 {
			margin-top: 60rpx;
			font-size: 26.16rpx;
			font-weight: 400;
			color: rgba(169, 164, 181, 1);
			display: flex;
			/* align-items: center; */
			justify-content: center;
		}

		.di-box {
			height: 117rpx;
			margin-top: 58rpx;
			display: flex;
			align-items: center;
			justify-content: center;
			border-top: 1.74rpx solid rgba(112, 112, 112, 1);
			
		}
	}
</style>