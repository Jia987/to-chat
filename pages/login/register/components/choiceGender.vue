<template>
	<view class="container">
		<input v-for="(digit, index) in codeDigits" :key="index" :focus="codeDigits[index].focus"
			:cursor='codeDigits[index].val ? codeDigits[index].val.length : 0' v-model="codeDigits[index].val"
			class="code-input" :class="[index===digit.indexActivate?'code-input-activate':'']" type="text" max="9"
			min="0" @input="handleInput(index)" @keydown.delete="handleDelete(index)" />
	</view>
</template>

<script>
	// 验证输入框
	export default {
		data() {
			return {
				codeDigits: [{
						val: '',
						focus: false,
						indexActivate: -1
					},
					{
						val: '',
						focus: false,
						indexActivate: -1
					},
					{
						val: '',
						focus: false,
						indexActivate: -1
					},
					{
						val: '',
						focus: false,
						indexActivate: -1
					},
				]
			};
		},
		methods: {
			handleInput(index) {
				this.codeDigits[index].indexActivate = index
				if (this.codeDigits[index].val.length >= 1 && index < this.codeDigits.length - 1) {
					this.codeDigits[index].focus = false;
					const nextIndex = index + 1;
					this.codeDigits[nextIndex].focus = true;
				}
				if(index === 3){
					console.log(index);
					this.emailVerification()
				}
			},
			handleDelete(index) {
				this.codeDigits[index].indexActivate = -1
				if (index > 0 && this.codeDigits[index].val.length === 0) {
					this.codeDigits[index].focus = false;
					const prevIndex = index - 1;
					this.codeDigits[prevIndex].focus = true;
				}
			},
			emailVerification(){
							console.log('-----------------');
				this.$emit('update:nextStep', "mailbox");
			} 
		}
	};
</script>

<style>
	.container {
		padding: 0 30rpx;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.code-input {
		width: 80rpx;
		height: 80rpx;
		text-align: center;
		font-size: 60rpx;
		margin: 0 28rpx;
		border-bottom: 2px solid rgba(138, 138, 138, 1);
	}

	.code-input-activate {
		border-bottom: 2px solid rgba(139, 92, 255, 1);
	}
</style>