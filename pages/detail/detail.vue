<template>
	<view class="">
		<swiperImage :autoplay="false" :resdata="swipers" :height="750"></swiperImage>
		<view class="d-flex flex-column ml-2 mb-2 mr-2">
			<text style="font-size: 38rpx;font-weight: 600;">小米MIX3 6GB+128GB</text>
			<text style="color: #B2B2B2;font-size: 30rpx;">磁动力滑盖全面屏/前后旗舰AI双摄/四曲面彩色陶瓷机身/高效10W无线充电</text>
			<view class="mt-2 d-flex" style="color: #ff6500;font-size: 32rpx;">
				<text style="font-size: 30rpx;">￥</text>
				<text style="font-weight: 800;font-size: 38rpx;">3299</text>
			</view>
		</view>
		<hardware :resdata="devices"></hardware>
		<selectDevices :services="services" :address="address" :devices="detype"></selectDevices>
		<detailCommons></detailCommons>
		<view class="d-flex a-center j-center" style=" color: #007BFF;height: 130rpx;">
			<view class="" style="font-size: 30rpx;">
				更多评论
			</view>
			<rightArrow arrcolor="#007BFF"></rightArrow>
		</view>
		<view class="d-flex flex-column">
			<image lazy-load mode="widthFix" src="../../static/static/images/demo/longimg.webp"></image>
			<image lazy-load mode="widthFix" src="../../static/static/images/demo/longimg2.webp"></image>
		</view>
		<view class="mt-3">
			<text style="font-size: 31rpx; margin-left: 20rpx;line-height: 75rpx;font-weight: 800;">为你推荐</text>
		</view>
		<view style="margin-bottom: 100rpx;">
			<goods :resdata="goods"></goods>
		</view>
		<view class="d-flex" style="position: fixed;bottom: 0;">
			<button type="default" plain style="background-color: #FFFFFF;font-size: 30rpx;height: 100rpx;width: 175rpx;border: none;border-radius: 0;">
				<view style="height: 100%;width: 100%;" class="d-flex flex-column a-center j-center">
					<image style="width: 30rpx;height: 30rpx;" src="../../static/static/font/heart.svg" mode=""></image>
					<text>收藏</text>
				</view>
			</button>
			<button type="default" plain style="background-color: #FFFFFF;font-size: 30rpx;height: 100rpx;width: 175rpx;border: none;border-radius: 0;">
				<view style="height: 100%;width: 100%;" class="d-flex flex-column a-center j-center">
					<image style="width: 30rpx;height: 30rpx;" src="../../static/static/font/shoppingcar.svg" mode=""></image>
					<text>购物车</text>
				</view>
			</button>
			<button type="default" plain style="color: #FFFFFF;line-height: 100rpx;font-size: 30rpx;height: 100rpx;background-color:#fd6900 ;width: 420rpx;border: none;border-radius: 0;">加入购物车</button>
		</view>
	</view>
</template>

<script>
	import rightArrow from "@/components/right-arrow.vue"
	import detailCommons from "@/components/detail/detail-commons.vue"
	import hardware from "@/components/detail/hardware.vue"
	import goods from "@/components/goods.vue"
	import swiperImage from "@/components/swiper-image.vue"
	import selectDevices from "@/components/detail/select-devices.vue"
	export default {
		components: {
			rightArrow,
			detailCommons,
			selectDevices,
			swiperImage,
			goods,
			hardware
		},
		data() {
			return {
				detype: {
					name: "火焰红64G标配"
				},
				address: {
					city: "北京",
					address: "昌平区",
					ishave: "ture"
				},
				services: [{
					name: "小米自营"
				}, {
					name: "小米发货"
				}, {
					name: "七天无理由退货"
				}, {
					name: "退换无忧"
				}],
				devices: [{
					name: "CPU",
					des: "骁龙855",
					url: "../../static/static/font/CPU.svg"
				}, {
					name: "高分屏",
					des: "4K高色域",
					url: "../../static/static/font/CPU.svg"
				}, {
					name: "大运存",
					des: "12GB",
					url: "../../static/static/font/CPU.svg"
				}, {
					name: "存储容量",
					des: "256GB",
					url: "../../static/static/font/CPU.svg"
				}, {
					name: "电池容量",
					des: "4000mAh",
					url: "../../static/static/font/CPU.svg"
				}, {
					name: "运营商网络",
					des: "5G全网通",
					url: "../../static/static/font/CPU.svg"
				}, {
					name: "三摄像头",
					des: "4800万像素",
					url: "../../static/static/font/CPU.svg"
				}],
				goods: [{
					src: "../../static/static/images/demo/list/5.jpg",
					money: "2199",
					title: "米家空调",
					des: "1.5匹支流变频",
					old: "￥2699"
				}, {
					src: "../../static/static/images/demo/list/5.jpg",
					money: "2199",
					title: "米家空调",
					des: "1.5匹支流变频",
					old: "￥2699"
				}, {
					src: "../../static/static/images/demo/list/5.jpg",
					money: "2199",
					title: "米家空调",
					des: "1.5匹支流变频",
					old: "￥2699"
				}, {
					src: "../../static/static/images/demo/list/5.jpg",
					money: "2199",
					title: "米家空调",
					des: "1.5匹支流变频",
					old: "￥2699"
				}],
				swipers: [{
					src: "../../static/static/images/demo/list/1.jpg"
				}, {
					src: "../../static/static/images/demo/list/2.jpg"
				}]
			}
		},
		methods: {

		}
	}
</script>

<style>

</style>
