<template>
	<view>
		<scroll-view class="mt-3" scroll-x="true" style="width: 100%;">
			<view class="d-flex ">
				<block v-for="(item,index) in 10" :key="index">
					<view class="p-3 ml-2" style="border:3rpx solid #F1F1F1;border-radius: 10rpx;width: 560rpx;height: 360rpx;background-color: #f5f6f3;">
						<view class="d-flex a-center j-sb" style="">
							<view class="d-flex a-center">
								<view style="width: 70rpx;height: 70rpx;background-size: 70rpx;background-image:url(../../static/static/images/demo/demo6.jpg);border-radius: 35rpx;">
								</view>
								<view class="ml-2">
									<view style="font-size: 30rpx;font-weight: 600;">楚绵</view>
									<view style="font-size: 25rpx;color:#b5b6b3 ;">2019-06-20</view>
								</view>
							</view>
							<view class="d-flex">
								<view class="">
									👍
								</view>
								<view style="color: #aeafac;">
									164
								</view>
							</view>
						</view>
						<view class="d-flex j-sb pt-5" style="">
							<image style="height: 175rpx;width: 175rpx;" src="../../static/static/images/demo/list/4.jpg" mode=""></image>
							<image style="height: 175rpx;width: 175rpx;" src="../../static/static/images/demo/list/4.jpg" mode=""></image>
							<image style="height: 175rpx;width: 175rpx;" src="../../static/static/images/demo/list/4.jpg" mode=""></image>
						</view>
					</view>
				</block>
			</view>
		</scroll-view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style>

</style>
