<template>
	<view class="mt-3 ml-2 mr-2" style="border: 2rpx solid #cecece;border-radius: 10rpx;">
		<button @tap="selectType" class="d-flex a-center j-sb" style="border-radius: 0;background-color: #F5F6f3 ;height: 90rpx;border-color: transparent transparent #cecece transparent;"
		 plain>
			<view>
				<text style="font-size: 30rpx;color: #878885;">已选</text>
				<text class="pl-2" style="color: #686d6e;font-size: 30rpx;">{{devices.name}}</text>
			</view>
			<rightArrow arrcolor="#bcbdba"></rightArrow>
		</button>
		<button @click="showBottom()">底部弹窗</button>
		<bottomSheet :isShowBottom="isShowBottom" @closeBottom="closeBottom"></bottomSheet>
		<button class="d-flex a-center j-sb" style="border-radius: 0;background-color: #F5F6f3 ;height: 90rpx;border-color: transparent transparent #cecece transparent;"
		 plain>
			<view class="">
				<text style="font-size: 30rpx;color: #878885;">配送</text>
				<text class="pl-2" style="color: #686d6e;font-size: 30rpx;">{{address.city}}</text>
				<text class="pl-2"></text>
				<text style="color: #686d6e;font-size: 30rpx;">{{address.address}}</text>
				<text class="pl-2" style="color: #ff6800;font-size: 30rpx;" v-if="address.ishave=='ture'">有现货</text>
				<text class="pl-2" style="color: #000000;font-size: 30rpx;" v-else>缺货</text>
			</view>
			<rightArrow arrcolor="#bcbdba"></rightArrow>
		</button>
		<button class="d-flex a-center j-sb" style="border-radius: 0;background-color: #F5F6f3 ;height: 90rpx;font-size: 28rpx;border-color: transparent transparent #cecece transparent;"
		 plain>
			<block v-for="(item,index) in services" :key="index">
				<view class="" v-if="index<3">
					<radio checked="ture" color="#ef5300" style="transform: scale(0.7);" />
					<text>{{item.name}}</text>
				</view>
			</block>
			<rightArrow arrcolor="#bcbdba"></rightArrow>
		</button>

	</view>
</template>

<script>
	import bottomSheet from "@/components/detail/bottomSheet.vue"
	import rightArrow from "@/components/right-arrow.vue"
	export default {
		components: {
			rightArrow,
			bottomSheet
		},
		props: {
			services: Array,
			address: Object,
			devices: Object
		},
		methods: {
			//底部开关
			showBottom() {
				this.isShowBottom = true;
			},
			closeBottom() {
				this.isShowBottom = false;
			},
			selectType() {

			}
		},
		data() {
			return {
				isShowBottom: false,
			};
		}
	}
</script>

<style>
	/* 隐藏滚动条 这个不能放在组件里*/
	::-webkit-scrollbar {
		width: 0;
		height: 0;
		color: transparent;
	}
</style>
