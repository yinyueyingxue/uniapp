<template>
	<view>
		<view class="row j-center mt-3">
			<block v-for="(item,index) in resdata" :key="index">
				<view class="d-flex flex-column span-4 a-center mb-3" @tap="event(item,index)">
					<image lazy-load="true" :src="item.src" style="height: 60rpx; width: 60rpx"></image>
					<text>{{item.text}}</text>
				</view>
			</block>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			};
		},
		props: {
			resdata: Array
		},
		methods: {
			event(item,index) {
				console.log("点击了"+item.src+"---"+(index+1))
			}
		}
	}
</script>

<style>

</style>
