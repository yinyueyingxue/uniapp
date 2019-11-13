<template>
	<view>
		<view class="">
			<text style="font-size: 31rpx; margin-left: 20rpx;line-height: 75rpx;font-weight: 800;">{{resdata.text}}</text>
		</view>
		<view class="" style="margin-top: 23rpx;margin-bottom: 23rpx;">
			<block v-for="(item,index) in resdata.buttons" :key="index">
				<button plain="true" size="mini" style="color: #717171;margin-left: 17rpx;background-color: #f5f5f5;border:0rpx;border-radius: 0">
					{{item.text}}
				</button>
			</block>
		</view>
	</view>
</template>

<script>
	export default {
		props: {
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
