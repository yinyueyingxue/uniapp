<template>
	<view>
		<scroll-view scroll-x="true" style="width: 100%;">
			<view class="d-flex">
				<block v-for="(item,index) in resdata" :key="index">
					<view class="d-flex flex-column pl-2 pr-2 j-center a-center" style="margin-left: 19rpx;">
						<image :src="item.url" style="width:30rpx; height: 30rpx;" mode=""></image>
						<view style="font-size:30rpx;white-space: nowrap;">{{item.name}}</view>
						<view class="" style="font-size: 20rpx;white-space: nowrap;">
							{{item.des}}
						</view>
					</view>
				</block>
			</view>
		</scroll-view>
	</view>
</template>

<script>
	export default {
		props:{
			resdata:Array
		},
		data() {
			return {
				
			};
		}
	}
</script>

<style>

</style>
