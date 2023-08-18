<template>
	<view style="background: rgba(246, 246, 246, 1);height: 100vh; ">
		<view class="lo-box">
			<Top></Top>
			<view class="lo-box-1" style="margin-top: 314rpx;">
				<input style="height: 109rpx;" type="text" placeholder="输入账号" placeholder-class="lo-placeholder">
			</view>
			<view class="lo-box-1" style="margin-top: 27rpx;">
				<input style="height: 109rpx;" type="text" placeholder="输入密码" placeholder-class="lo-placeholder">
			</view>
			<view class="lo-box-2" @click="appear">
				<text class="lo-text-1">忘记密码？</text>
			</view>
			<btn :active="active" text="注册"></btn>
			<protocols :active="active" @update:active="show"></protocols>
			<view class="lo-box-4">
				<view class="lo-text-4" style="margin-left:38rpx ;"
					@click="navigator_btn('/pages/login/register/register')">注册</view>
				<!-- 			<view class="lo-text-4">邮箱登录</view> -->
				<view class="lo-text-4" style="margin-right: 12rpx;">忘记密码</view>
			</view>
		<!-- 	  <button @click="showDialog">显示弹框</button>
			<myDialog :visible="dialogVisible" @close="closeDialog">
		
			</myDialog> -->
		</view>
	</view>
</template>

<script>
	import Top from './components/top.vue'
	import protocols from './components/protocols.vue'
	import btn from './components/btn.vue'
	import myDialog from './components/myDialog.vue'
	export default {
		components: {
			Top,
			protocols,
			btn,
			myDialog
		},

		data() {
			return {
				isshow: false,
				active: false,
				dialogVisible: false,
			}
		},
		methods: {
			choice() {
				this.isshow = !this.isshow

			},
			navigator_btn(url) {
				uni.navigateTo({
					url: url
				})
			},
			show(v) {
				this.active = v
			},
			showDialog() {
				this.dialogVisible = true;
			},
			closeDialog() {
				this.dialogVisible = false;
			}

		}
	}
</script>

<style scoped lang="scss">
	.lo-box {
		padding: 0 90rpx;

		.lo-img {
			width: 52rpx;
			height: 42rpx;
			margin-top: 113rpx;
			margin-left: 22rpx;
		}

		.lo-text {
			margin-top: 23rpx;
			font-size: 52.33rpx;
			font-weight: 400;
			display: flex;
			align-items: center;
			justify-content: center;
		}

		.lo-box-1 {

			background: rgba(255, 255, 255, 1);
			border-radius: 20.93rpx;
			box-shadow: 0rpx 6.98rpx 20.93rpx rgba(0, 0, 0, 0.03);
			display: flex;
			justify-content: center;

			.lo-placeholder {
				font-size: 31.4rpx;
				font-weight: 500;
				color: rgba(169, 164, 181, 1);
				text-align: center;
			}
		}

		.lo-box-2 {
			margin-top: 19rpx;
			display: flex;
			justify-content: right;

			.lo-text-1 {
				font-size: 27.91rpx;
				font-weight: 400;
				line-height: 40.41rpx;
				color: rgba(0, 93, 255, 1);

			}
		}

		.lo-button {
			margin-top: 74rpx;
			height: 109rpx;
			background: rgba(0, 158, 255, 1);
			border-radius: 20.93rpx;
			font-size: 31.4rpx;
			color: rgba(255, 255, 255, 1);
			font-weight: 500;
			display: flex;
			align-items: center;
			justify-content: center;
		}

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

		.lo-box-4 {
			margin-top: 417rpx;
			display: flex;
			justify-content: space-between;
			align-items: center;

			.lo-text-4 {
				font-size: 26.16rpx;
				font-weight: 400;
				color: rgba(110, 110, 110, 1);
			}
		}
	}
</style>