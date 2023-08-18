<template>
	<view class="au-box">
		<view class="au-text">
			<text space='ensp'>正在给</text><text style="color:rgba(61, 145, 255, 1) ;">{{mail}}</text><text>发送邮件</text>
		</view>
		<choiceGender @update:nextStep="nextStep"></choiceGender>
		<view class="au-text-1">
			<text>请 52s 后重试</text>
		</view>
	</view>
</template>

<script>
	// 邮箱验证码输入
	import choiceGender from './choiceGender.vue'
	export default {
		components: {
			choiceGender
		},
		props: {
			mail: {
				type: String,
				default: '934598656@qq.com'
			}
		},
		data() {
			return {

			}
		},
		methods: {
			nextStep(vla) {
				this.$emit('update:nextStep', vla);
				console.log('----------123-------');
			}
		}
	}
</script>


<style scoped lang="scss">
	.au-box {
		// width: 570rpx;
		// height: 438rpx;
		margin-top: 300rpx;
		background: #fff;
		box-shadow: 0rpx 6.98rpx 20.93rpx rgba(0, 0, 0, 0.03);
		border-radius: 57.56rpx;
		display: flex;
		padding: 40rpx;
		flex-direction: column;
		justify-content: space-between;

		.au-text {
			font-size: 28rpx;
			margin-bottom: 71rpx;
		}

		.au-text-1 {
			margin-top: 102rpx;
			font-size: 24.42rpx;
			color: rgba(139, 92, 255, 1);
			text-align: right;
		}

	}
</style>