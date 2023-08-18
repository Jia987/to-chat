<template>
	<view class="re-box" style="background: rgba(246, 246, 246, 1);height: 100vh; ">
		<Top text="注册"></Top>
		<!-- 		<template v-if="nextStep ==='agreeContinue'">
			<emailInput></emailInput>
			<view class="bt-box">
				<button :disabled="!active" type="primary" @click="forward('authCode')">同意并继续</button>
			</view>
			<protocols :active="active" @update:active="show"></protocols>
		</template>
		<template v-else-if="nextStep ==='authCode'">
			<authCode  @update:nextStep='forward'></authCode>
		</template>
		<template v-else-if="nextStep ==='mailbox'">
			<mailbox class="re-box-1"></mailbox>
		</template> -->

	<sexSelection></sexSelection>

	</view>
</template>

<script>
	import Top from '../components/top.vue'
	import emailInput from './components/emailInput.vue'
	import protocols from '../components/protocols.vue'
	import btn from '../components/btn.vue'
	import mailbox from './components/mailbox.vue'
	import authCode from './components/authCode.vue'
	import sexSelection from './components/sexSelection.vue'
	export default {
		components: {
			Top,
			emailInput,
			protocols,
			btn,
			mailbox,
			authCode,
			sexSelection
		},
		data() {
			return {
				active: false,
				nextStep: 'agreeContinue',
			};
		},
		methods: {
			show(v) {
				this.active = v
			},
			forward(vla) {
				console.log(vla);
				this.nextStep = vla
			}
		},
	}
</script>

<style lang="scss" scoped>
	.bt-box {
		margin-top: 120rpx;
	}

	.re-box {
		padding: 0 90rpx;
	}

	.re-box-1 {
		margin-top: 220rpx;
	}

	.re-button {
		background: rgba(123, 201, 249, 1);
		border-radius: 20.93rpx;
	}
</style>