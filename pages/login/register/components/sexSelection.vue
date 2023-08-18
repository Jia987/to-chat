<template>
	<view>
		<view class="sex-box">
			<view class="sex-text">
				<view @click="onSex(1)" class="sex-box-1" :class="[sex===1?'sex-box-2':'']">
					<image style="width: 100rpx; height: 100rpx;" src="../../../../static/login/register/register-2.jpg"
						mode=""></image>
				</view>
				<text :class="[sex===1?'sex-text-1':'']">男孩</text>
			</view>
			<view class="sex-text">
				<view @click="onSex(2)" class="sex-box-3" :class="[sex===2?'sex-box-2':'']">
					<image style="width: 100rpx; height: 100rpx;" src="../../../../static/login/register/register-1.jpg"
						mode=""></image>
				</view>
				<text :class="[sex===2?'sex-text-1':'']">女孩</text>
			</view>



		</view>

		<btn text="下一步"></btn>
	</view>
</template>

<script>
	import btn from '../../components/btn.vue'
	export default {
		components: {
			btn
		},
		data() {
			return {
				sex: 0
			}
		},
		methods: {
			onSex(vla) {
				this.sex = vla
			}
		}
	}
</script>

<style scoped lang="scss">
	.sex-box {
		margin-top: 378rpx;
		margin-bottom: 200rpx;
		display: flex;
		justify-content: space-between;

		.sex-box-1 {
			width: 162.21rpx;
			height: 155.23rpx;
			border-radius: 57.56rpx;
			background: rgba(255, 255, 255, 1);
			display: flex;
			align-items: center;
			justify-content: center;
			// flex-direction: column; // 垂直布局
			margin-bottom: 12rpx;
		}

		.sex-box-3 {
			width: 162.21rpx;
			height: 155.23rpx;
			border-radius: 78.49rpx;
			background: rgba(255, 255, 255, 1);
			display: flex;
			align-items: center;
			justify-content: center;
			// flex-direction: column; // 垂直布局
			margin-bottom: 12rpx;
		}

		.sex-box-2 {
			background: rgba(225, 225, 225, 1);
		}

		.sex-text {
			font-size: 36.63rpx;
			font-weight: 700;
			text-align: center;
			color: rgba(148, 148, 148, 1);
		}

		.sex-text-1 {
			color: #000;
		}
	}
</style>