<template>
	<view class="" style="background: rgba(246, 246, 246, 1)">
		<image class="lo-img" v-show="isShow" src="/static/login/login-1.png" mode="">
		</image>
		<view class="lo-text" :class="[isShow!==true?'lo-mar':'']">{{text}}</view>
	</view>
</template>

<script>
	export default {

		props: {
			text: {
				type: String,
				default: '登录'
			},
			isShow: {
				type: Boolean,
				default: true
			}
		},

		data() {
			return {}
		},
		methods: {
			choice() {
				this.isshow = !this.isshow
			}
		}
	}
</script>

<style scoped lang="scss">
	.lo-img {
		width: 52rpx;
		height: 42rpx;
		margin-top: 113rpx;
		margin-bottom: 23rpx;
	}

	.lo-mar {
		padding-top: 178rpx;
	}

	.lo-text {
		font-size: 52.33rpx;
		font-weight: 400;
		display: flex;
		align-items: center;
		justify-content: center;
	}
</style>