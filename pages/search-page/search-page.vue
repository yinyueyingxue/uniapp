<template>
	<view class="">
		<uniDrawer :visible="visible" mode="right" @close="declose()">
			<view style="padding:25rpx;">
				<block v-for="(item,index) in searchtypes" :key="index">
					<view class="" style="margin-bottom: 69rpx;">
						<text>{{item.title}}</text>
						<view class="mt-4 d-flex j-sb">
							<block v-for="(item2,index2) in item.type" :key="index2">
								<button v-if="item2.isc" plain="true" style="border-radius: 0;font-size: 24rpx;line-height: 71rpx;width: 164rpx;height: 71rpx;background-color: #fce1d5;color: #ee7726;border-color: #fb7414;"
								 size="mini" @tap="buttoned(item2.isc,item2,index,index2)">{{item2.name}}</button>
								<button v-else plain="true" style="border-radius: 0;font-size: 24rpx;line-height: 71rpx;width: 164rpx;height: 71rpx;"
								 size="mini" @tap="buttoned(item2.isc,item2,index,index2)">{{item2.name}}</button>
							</block>
						</view>
					</view>
				</block>
			</view>
			<view class="d-flex" style="position: fixed;bottom: 0;">
				<button @tap="reset" plain="true" type="default" style="width: 300rpx;height: 90rpx;border-radius: 0;border: 0rpx solid #FFFFFF;">重置</button>
				<button @tap="submit" plain="true" type="default" style="width: 300rpx;height: 90rpx;border-radius: 0;border: 0rpx solid #FFFFFF;background-color:#fd6900 ;">确定</button>
			</view>
		</uniDrawer>
		<selectTop :resdata="selectitems" v-on:isshow="isShow"></selectTop>
		<searchGoods :resdata="searchgoods"></searchGoods>
	</view>
</template>

<script>
	import selectTop from "@/components/select-top.vue"
	import searchGoods from "@/components/search/search-goods.vue"
	import uniDrawer from "@/components/uni-drawer.vue"
	export default {
		components: {
			selectTop,
			searchGoods,
			uniDrawer
		},
		data() {
			return {
				visible: "",
				searchtypes: [{
					title: "服务",
					type: [{
						name: "促销",
						isc: false
					}, {
						name: "分期",
						isc: false
					}, {
						name: "仅看有货",
						isc: false
					}]
				}, {
					title: "分类",
					type: [{
						name: "耳机",
						isc: false
					}, {
						name: "户外",
						isc: false
					}, {
						name: "配件",
						isc: false
					}]
				}],
				searchgoods: [{
					url: "../../static/static/images/demo/list/5.jpg",
					title: "真无线蓝牙耳机",
					des: "描述/描述/描述/描述/描述/描述/描述/描述/描述/描述/描述/描述",
					money: "199",
					common: "1465评论 98%满意"
				}, {
					url: "../../static/static/images/demo/list/5.jpg",
					title: "真无线蓝牙耳机",
					des: "描述/描述/描述",
					money: "199",
					common: "1465评论 98%满意"
				}, {
					url: "../../static/static/images/demo/list/5.jpg",
					title: "真无线蓝牙耳机",
					des: "描述/描述/描述",
					money: "199",
					common: "1465评论 98%满意"
				}, {
					url: "../../static/static/images/demo/list/5.jpg",
					title: "真无线蓝牙耳机",
					des: "描述/描述/描述",
					money: "199",
					common: "1465评论 98%满意"
				}, {
					url: "../../static/static/images/demo/list/5.jpg",
					title: "真无线蓝牙耳机",
					des: "描述/描述/描述",
					money: "199",
					common: "1465评论 98%满意"
				}, {
					url: "../../static/static/images/demo/list/5.jpg",
					title: "真无线蓝牙耳机",
					des: "描述/描述/描述",
					money: "199",
					common: "1465评论 98%满意"
				}],
				selectitems: [{
					title: "综合",
					cir: true,
					selected: 0
				}, {
					title: "销量",
					cir: true,
					selected: 0
				}, {
					title: "价格",
					cir: true,
					selected: 0
				}, {
					title: "筛选",
					cir: false,
					selected: 0
				}]
			}
		},
		methods: {
			submit:function(){
				this.visible=false;
			},
			reset:function(){
				uni.navigateTo({
					url:'../search-page/search-page'
				})
			},
			isShow: function(current) {
				this.visible = current;
				// console.log("father___"+this.visible)
			},
			declose: function() {
				this.visible = false;
				// console.log("...."+this.visible)
			},
			buttoned: function(isc, item, index, index2) {
				this.searchtypes[index].type[index2].isc = !isc
				// console.log("isc:" + isc);
				// console.log(item);
			}
		}
	}
</script>

<style>
	.sc-color {
		background-color: #fce1d5;
		color: #ee7726;
		border-color: #fb7414;
	}
</style>
