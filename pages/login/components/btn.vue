<template>
	<view class="bt-box">
		<button :disabled="!active" type="primary">{{text}}</button>
	</view>
</template>

<script>
	export default {
		props: {
			text: {
				type: String,
				default: '同意并继续'
			},
			active: {
				type: Boolean,
				default: true
			},
			nextStep: {
				type: String,
				default: ''
			}
		},

		data() {
			return {}
		},
		methods: {
			choice() {
				this.$emit('update:show', true);
				this.active = !this.active			
			}
		}
	}
</script>

<style scoped lang="scss">
	.bt-box {
		margin-top: 120rpx;
	}
</style>