<template>
	<view class="" style="margin-top: 23rpx;margin-bottom: 23rpx;">
		<block v-for="(item,index) in resdata" :key="index">
			<button v-if="item.type==1" plain="true" size="mini" style="margin-left: 17rpx;background-color: #f7ece8;border:2rpx solid #f2a5a8;border-radius: 0">
				{{item.text}}
			</button>
			<button v-if="item.type==2" plain="true" size="mini" style="margin-left: 17rpx; background-color: #e8f7f5;border:2rpx solid #94d7da;border-radius: 0">
				{{item.text}}
			</button>
			<button v-if="item.type==3" plain="true" size="mini" style="margin-left: 17rpx;background-color: #f1f7e8;border:2rpx solid #bcce95;border-radius: 0">
				{{item.text}}
			</button>
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
