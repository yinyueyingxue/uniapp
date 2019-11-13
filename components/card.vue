<template>
	<view class="d-flex" style="height: 529rpx;">
		<view style="margin-right: 2rpx;">
			<image lazy-load="true" :src="resdata.left.src" style="width: 373rpx ;height: 529rpx ;" mode=""></image>
		</view>
		<view class="flex-column">
			<view class="" style="height:263rpx">
				<image lazy-load="true" :src="resdata.rt.src" style="width: 375rpx;height:263rpx ;"></image>
			</view>
			<view class="" style="height:263rpx;margin-top: 1rpx;">
				<image lazy-load="true" :src="resdata.rb.src" style="width: 375rpx;height:263rpx ;"></image>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		props:{
			resdata:Object,
		},
		data() {
			return {
			};
		}
	}
</script>

<style>

</style>
