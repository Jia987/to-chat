<template>
	<view class="email-input">
		<view class="re-box-1">
			<input type="text" style="width: 240rpx;" placeholder="请输入邮箱" placeholder-class="re-placeholder">
			<image @click="handleInput()" style="width:  19rpx; height:10rpx;" src="@/static/login/register/login-4.png"
				mode="">
			</image>
			<view class="re-box-2">
				<text style="font-size: 22.6rpx; margin-left:5rpx; margin-right: 15rpx;"> {{ email }}</text>
				<view v-show="showDropdown" class="email-dropdown">
					<view v-for="(suffix, index) in emailSuffixes" :key="index" @tap="selectEmailSuffix(suffix)">
						{{ suffix }}
					</view>
				</view>
			</view>
				
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				email: '@gmail.com',
				showDropdown: false,
				emailSuffixes: ['@gmail.com', '@yahoo.com', '@hotmail.com', '@outlook.com', '@example.com'],
			};
		},
		methods: {
			handleInput() {
				this.showDropdown = true;
			},
			selectEmailSuffix(suffix) {
				this.email = suffix;
				this.showDropdown = false;
			},
		},
	};
</script>

<style scoped lang="scss">
	.email-input {
		position: relative;
	}

	.email-dropdown {
		position: absolute;
		background-color: #fff;
		// border: 1px solid #ccc;
		padding: 0;
		margin: 0;
		top: 70%;
		left: 100;
		width: 200rpx;
		// box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
		// text-align: right;
		font-size: 22.6rpx;
		border-radius: 23.08rpx;
	}

	.email-dropdown view {
		padding: 2px 2px;
		cursor: pointer;
	}

	.email-dropdown view:hover {
		background-color: #f0f0f0;

	}

	.re-box-2 {
		display: flex;
		align-items: center;
	}

	.re-box-1 {
		margin-top: 314rpx;
		background: #fff;
		border-radius: 23.08rpx;
		border: 1.92rpx solid rgba(246, 246, 246, 1);
		height: 109rpx;
		display: flex;
		align-items: center;
		justify-content: right;
	}

	.re-placeholder {
		color: rgba(169, 164, 181, 1);
		font-size: 34.62rpx;
		font-weight: 500;
	}
</style>