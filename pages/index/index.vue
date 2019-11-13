<template>
	<view>
		<tabbar></tabbar>
		<!-- 首页面 -->
		<swiperImage :autoplay="true" :resdata="swipers" :height="350"></swiperImage>
		<indexNav :resdata="navs"></indexNav>
		<line></line>
		<card :resdata="cards"></card>
		<line></line>
		<news :resdata="news"></news>
		<goods :resdata="goods"></goods>
	</view>
</template>

<script>
	import tabbar from "@/components/tabbar.vue"
	import swiperImage from "@/components/swiper-image.vue"
	import indexNav from "@/components/index-nav.vue"
	import line from "@/components/line.vue"
	import card from "@/components/card.vue"
	import news from "@/components/news.vue"
	import goods from "@/components/goods.vue"
	export default {
		components: {
			tabbar,
			swiperImage,
			indexNav,
			line,
			card,
			news,
			goods
		},
		onNavigationBarSearchInputClicked() {
			console.log("进入搜索页");
			uni.navigateTo({
				url: '../search/search'
			});
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
				cards: {
					left: {
						src: "../../static/static/images/demo/demo1.jpg"
					},
					rt: {
						src: "../../static/static/images/demo/demo2.jpg"
					},
					rb: {
						src: "../../static/static/images/demo/demo3.jpg"
					}
				},
				news: {
					text: "每日精选",
					src: "../../static/static/images/demo/demo4.jpg"
				},
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
				}]
			}
		}
	}
</script>

<style>

</style>
