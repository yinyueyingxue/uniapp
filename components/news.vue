<template>
	<view class="">
		<text style="font-size: 31rpx; margin-left: 20rpx;line-height: 75rpx;font-weight: 800;">{{resdata.text}}</text>
		<view class="" style="height: 300rpx;margin-bottom: 1rpx ;">
			<image lazy-load="true" :src="resdata.src" style="height: 300rpx;" mode=""></image>
		</view>
	</view>
</template>

<script>
	export default {
		props:{
			resdata:Object
		},
		data() {
			return {
				
			};
		}
	}
</script>

<style>

</style>
