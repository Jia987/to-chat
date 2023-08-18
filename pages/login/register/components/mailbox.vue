<template>
	<view class="background">
		<picker-view class="picker-view" v-if="visible" :indicator-style="indicatorStyle" :value="value"
			@change="bindChange">
			<picker-view-column>
				<view class="item" v-for="(item,index) in years" :key="index">{{item}}年</view>
			</picker-view-column>
			<picker-view-column>
				<view class="item" v-for="(item,index) in months" :key="index">{{item}}月</view>
			</picker-view-column>
			<picker-view-column>
				<view class="item" v-for="(item,index) in days" :key="index">{{item}}日</view>
			</picker-view-column>
		</picker-view>
		<btn text="下一步"></btn>
		<view class="ma-box">
			<text>跳过</text>
		</view>

	</view>
</template>

<script>
	// 时间选择器
	import btn from '../../components/btn.vue'
	export default {
		components: {
			btn
		},

		data() {
			return {
				years: [],
				year: 0,
				months: [],
				month: 0,
				days: [],
				day: 0,
				visible: true,
				value: [],
				indicatorStyle: `height: 50px;`
			};
		},
		created() {
			var date = new Date()
			this.year = date.getFullYear()
			this.month = date.getMonth() + 1
			this.day = date.getDate()
			for (let i = 1990; i <= date.getFullYear(); i++) {
				this.years.push(i)
			}
			for (let i = 1; i <= 12; i++) {
				this.months.push(i)
			}
			for (let i = 1; i <= 31; i++) {
				this.days.push(i)
			}
			this.value = [9999, this.month - 1, this.day - 1]
		},
		methods: {
			bindChange(e) {
				const val = e.detail.value
				this.year = this.years[val[0]]
				this.month = this.months[val[1]]
				this.day = this.days[val[2]]
			}
		}
	}
</script>

<style scoped lang="scss">
	.picker-view {
		// width: 610rpx;
		height: 438rpx;

		background: #fff;
		overflow: hidden;
		/* 隐藏溢出内容 */
		border-radius: 38.37rpx;
		box-shadow: 0rpx 6.98rpx 20.93rpx rgba(0, 0, 0, 0.03)
	}

	.item {
		display: flex;
		align-items: center;
		justify-content: center;
		line-height: 32.7rpx;
		color: rgba(85, 76, 95, 1);
		font-size: 27.91rpx;
		font-weight: 400;
	}

	.ma-box {
		margin-top: 31rpx;
		color: rgba(41, 173, 255, 1);
		font-size: 29.65rpx;
		text-align: right;
	}
</style>