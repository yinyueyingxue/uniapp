<template>
	<view>
		<news :resdata="news"></news>
		<hotButton :resdata="hotbuttons"></hotButton>
		<textButton :resdata="textbuttons"></textButton>
		<line></line>
		<searchHistory :resdata="searchhistorys"></searchHistory>
	</view>
</template>

<script>
	import line from "@/components/line.vue"
	import searchHistory from "@/components/search-history.vue"
	import textButton from "@/components/text-button.vue"
	import hotButton from "@/components/hot-button.vue"
	import news from "@/components/news.vue"
	export default {
		components: {
			line,
			searchHistory,
			textButton,
			hotButton,
			news
		},
		onNavigationBarSearchInputChanged(data) {
			console.log(data);
			this.search = data
			console.log("键入文字");
		},
		onNavigationBarSearchInputConfirmed() {},
		onNavigationBarButtonTap() {
			console.log("按钮点击");
			console.log("..." + this.search.text + "...");
			uni.navigateTo({
				url: '../search-page/search-page',
				animationType: 'zoom-fade-out',
			});
		},
		data() {
			return {
				search: {},
				searchhistorys: {
					text: "搜索记录",
					historys: [{
						text: "小米"
					}, {
						text: "小米2"
					}]
				},
				textbuttons: {
					text: "常用分类",
					buttons: [{
						text: "耳机"
					}, {
						text: "手机"
					}, {
						text: "音响"
					}, {
						text: "手表"
					}, {
						text: "配件"
					}, {
						text: "网关/传感器"
					}, {
						text: "健康"
					}, {
						text: "潮玩"
					}]
				},
				news: {
					text: "热门搜索",
					src: "../../static/static/images/demo/demo4.jpg"
				},
				hotbuttons: [{
					type: 1,
					text: "领券中心"
				}, {
					type: 2,
					text: "Redmi K20"
				}, {
					type: 3,
					text: "RedmiBook 14"
				}, {
					type: 1,
					text: "智能积木 越野四驱车"
				}, {
					type: 1,
					text: "手环 腕带"
				}]
			}
		},
		methods: {

		}
	}
</script>

<style>

</style>
