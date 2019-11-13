<template>
	<view class="">
		<block v-for="(item,index) in resdata" :key="index">
			<view class="d-flex" style="border-bottom: 2rpx solid #F1F1F1; margin-top: 25rpx;margin-left: 18rpx; margin-bottom: 18rpx;">
				<view class="">
					<image lazy-load="true" style="width: 251rpx;height: 251rpx;" :src="item.url"
					 mode=""></image>
				</view>
				<view class="ml-3 mt-2 d-flex flex-column" style="margin-bottom: 18rpx;justify-content: space-around;">
					<text style="font-weight: 700;font-size: 35rpx;color:#343b40 ;">{{item.title}}</text>
					<text style="width: 408rpx;color: #6b767b; font-size: 24rpx;">{{item.des}}</text>
					<view class="d-flex j-start">
						<text style="font-size:24rpx;color: #ff6800;">￥</text>
						<text style="font-size:30rpx;color: #ff6800;">{{item.money}}</text>
					</view>
					<text style="font-size: 24rpx;color: #6b767b;">{{item.common}}</text>
				</view>
			</view>
		</block>
	</view>
</template>

<script>
	export default {
		props: {
			resdata: Array
		},
		data() {
			return {

			};
		}
	}
</script>

<style>

</style>
