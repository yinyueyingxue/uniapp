<template>
	<view class="d-flex flex-wrap j-sb">
		<block v-for="(item,index) in resdata" :key="index">
			<view  style="width: 370rpx;">
				<view class="" style="height: 370rpx;">
					<image lazy-load="true" :src="item.src" style="height: 370rpx;" mode=""></image>
				</view>
				<view class="flex-column j-sb" style="margin-top:23rpx ;margin-left: 18rpx;height: 163rpx;">
					<view class="">
						<text style="font-size: 28rpx; font-weight: 800;">{{item.title}}</text>
					</view>
					<view class="">
						<text style="font-size: 20rpx;">{{item.des}}</text>
					</view>
					<view class="d-flex" style="margin-top: 10rpx;">
						<text class="" style="font-size: 16rpx; color: #d44200;align-items:flex-start">￥</text>
						<text style="font-size: 26rpx; color: #d44200;align-items:flex-start">{{item.money}}</text>
						<view class="">
							<text class="ml-1" style="font-size: 18rpx; color: #bcbcbc;">{{item.old}}</text>
						</view>
					</view>
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
