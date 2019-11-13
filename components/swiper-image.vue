<template>
	<view>
		<swiper circular="true" :style="{height: height+'rpx'}" indicator-dots="true" :autoplay=autoplay interval="2000" duration="500">
			<block v-for="(item,index) in resdata" :key="index">
				<swiper-item>
					<view  @tap="event(item)" >
						<image :src="item.src" :style="{height: height+'rpx'}" lazy-load></image>
					</view>
				</swiper-item>
			</block>
		</swiper>
	</view>
</template>

<script>
	export default {
		props:{
			resdata: Array,
			height:Number,
			autoplay:Boolean
		},
		data() {
			return {
				
			};
		},
		methods:{
			event(item){
				console.log("轮播图被点击了--"+item.src+"-"+this.autoplay+"-"+this.height);
				uni.navigateTo({
					url:"../detail/detail"
				})
			}
		}
	}
</script>

<style>

</style>
