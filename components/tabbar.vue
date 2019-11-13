<template>
	<view>
		<view class="header-cate">
			<scroll-view class="menus" scroll-x="true">
				<view v-for="(menu, indexs) in categories" :key="indexs" :class="[indexs == currentIndex ? 'menuActive' : '']" @tap="taps(indexs)">
					<view :class="[indexs == currentIndex ? 'borderActive' : '']">{{menu.name}}</view>
				</view>
			</scroll-view>
<!-- 			<swiper :current="currentIndex">
				<swiper-item>
					<view class="swiper-item">
						<view class="">
							1
							<swiperImage :resdata="swipers"></swiperImage>
							<indexNav :resdata="navs"></indexNav>
						</view>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item">2</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item">3</view>
				</swiper-item>
			</swiper> -->
		</view>
	</view>
</template>
<script>
	import swiperImage from "@/components/swiper-image.vue"
	import indexNav from "@/components/index-nav.vue"
	export default {
		components: {
			swiperImage,
			indexNav
		},
		data() {
			return {
				swipers: [{
					src: "../../static/static/images/demo/demo4.jpg"
				}, {
					src: "../../static/static/images/demo/demo8.jpg"
				}],
				navs: [{
					src: "../../static/static/images/indexnav/1.png",
					text: "新品分类"
				}, {
					text: "小米众筹",
					src: "../../static/static/images/indexnav/2.gif"
				}, {
					text: "以旧换新",
					src: "../../static/static/images/indexnav/3.gif"
				}, {
					text: "一分拼团",
					src: "../../static/static/images/indexnav/4.gif"
				}, {
					text: "超值特卖",
					src: "../../static/static/images/indexnav/5.gif"
				}, {
					text: "小米秒杀",
					src: "../../static/static/images/indexnav/6.gif"
				}, {
					text: "真心想要",
					src: "../../static/static/images/indexnav/7.gif"
				}, {
					text: "电视特卖",
					src: "../../static/static/images/indexnav/8.gif"
				}, {
					text: "家电热卖",
					src: "../../static/static/images/indexnav/9.gif"
				}, {
					text: "米粉卡",
					src: "../../static/static/images/indexnav/10.gif"
				}],
				currentIndex: 0,
				categories: [{
						cateId: 0,
						name: "首页"
					},
					{
						cateId: 1,
						name: "数码"
					},
					{
						cateId: 2,
						name: "男装"
					},
					{
						cateId: 3,
						name: "家装"
					},
					{
						cateId: 4,
						name: "食品"
					},
					{
						cateId: 5,
						name: "百货"
					}, {
						cateId: 6,
						name: "箱包"
					},
				]
			}
		},
		methods: {
			taps(e) {
				console.log(e);
				this.currentIndex = e;
			}
		}
	}
</script>

<style>
	/* 首页分段器 */
	.header-cate {
		width: 100%;
		height: 88rpx;
		background: #FFF;
		border-bottom: 2rpx solid #F0F0F0;
		/* position: fixed; */
		/* z-index: 1; */
		/* left: 0; */
		/* top: 100rpx; */
	}

	/* 头部滚蛋菜单 */
	.menus {
		white-space: nowrap;
		text-align: center;
	}

	.menus view {
		margin-right: 30rpx;
		width: auto;
		line-height: 88rpx;
		display: inline-block;
		text-align: center;
		font-size: 30rpx;
	}

	.menus view:first-child {
		margin-left: 30rpx;
	}

	.menus view:last-child {
		margin-right: 30rpx;
	}

	.menuActive {
		color: #f36e00;
	}

	.borderActive {
		width: 60rpx;
		height: 88rpx;
		border-bottom: 2rpx solid #f36e00 !important;
	}

	/* 文字相关 */
	.center {
		justify-content: center;
		text-align: center;
	}
</style>
