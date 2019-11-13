<template>
	<view class="">
		<block v-for="(item,index) in 3" :key="index">
			<view class="d-flex a-center j-start" style="border: 1rpx #F1F1F1 solid;">
				<radio color="#fd6900" style="margin-left: 30rpx;"></radio>
				<view class="" style="margin: 30rpx;width: 190rpx;height: 190rpx;border: 2rpx #F1F1F1 solid;">
					<image style="width: 150rpx;height: 150rpx;padding: 20rpx;" src="../../static/static/images/demo/list/4.jpg" mode=""></image>
				</view>
				<view class="d-flex flex-column" style="">
					<text>商品标题1</text>
					<view>火焰红 64GB 标配</view>
					<view class="">
						<text>￥</text>
						<text>336 </text>
					</view>
				</view>
				<view class="example-body a-self-end pb-3" style="">
					<uni-number-box :value="numberValue" @change="change" />
				</view>
			</view>
		</block>
	</view>
</template>

<script>
	import uniNumberBox from "@/components/num-box/number-box.vue"
	export default {
		components: {
			uniNumberBox
		},
		data() {
			return {
				numberValue: 0
			}
		},
		methods: {
			change(value) {
				this.numberValue = value
			}
		}
	}
</script>

<style>

</style>
