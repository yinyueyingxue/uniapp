<template>
	<view class="d-flex" style="height: 100%;">
		<view class="" style="width: 165rpx;">
			<scroll-view scroll-with-animation :scroll-top="scoL" @scroll="leftsc" scroll-y="true" style="width: 165rpx;height: 100%;">
				<block v-for="(item,index) in 20" :key="index">
					<view @tap="clickL(index)" style="background-color: #fefefe;font-weight: 700;height: 100rpx;width: 165rpx;border-bottom: 2rpx #f4f4f4 solid;text-align: center;">
						<view style="line-height: 60rpx; height: 60%;position: relative;top: 20%;" :class="{checkL:index===currentL}">
							分类{{index}}
						</view>
					</view>
				</block>
			</scroll-view>
		</view>
		<view class="" style="width: 585rpx;">
			<scroll-view scroll-with-animation @scrolltolower="Rbottom" :scroll-top="scoR" @scroll="rightsc" scroll-y="true"
			 style="width: auto;height: 100%;">
				<block v-for="(item,index) in 20" :key="index">
					<view :id="'R-'+index" class="" style=" padding-top: 30rpx;height: 30rpx;line-height: 30rpx;">
						分类{{item}}
					</view>
					<view class="d-flex flex-wrap" style="border-bottom: 1rpx darkgrey solid;">
						<block v-for="(item2,index2) in 10" :key="index2">
							<view class="" style="margin: 33rpx;width: 120rpx;height:170rpx">
								<view class="" style="height: 120rpx;width: 120rpx;">
									<image lazy-load="true" src="../../static/static/images/demo/cate_08.png" mode="" style="height: 120rpx;width: 120rpx;"></image>
								</view>
								<view class="" style="">
									<text style="font-size: 25rpx; white-space: nowrap;">分类{{item}}:商品</text>
								</view>
							</view>
						</block>
					</view>
				</block>
			</scroll-view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				currentL: 0,
				scoL: 0,
				scoR: 0,
				heightR: 0,
				oldL: 0,
				oldR: 0,
				Tlist: []
			}
		},
		onLoad() {
			// console.log("已加载")
			// uni.getSystemInfo({
			// 	success: function(res) {
			// 		console.log(res.windowHeight)
			// 	}
			// });
			for (var index = 0; index < 20; index++) {
				const query = uni.createSelectorQuery().in(this);
				query.select("#R-" + index).boundingClientRect(data => {
					// console.log("得到布局位置信息" + JSON.stringify(data));
					// console.log("节点离页面顶部的距离为" + data.top);
					this.Tlist.push(data.top);
				}).exec();
				// console.log(index);
				// console.log("...");
			}
		},
		methods: {
			leftsc(e) {
				// console.log("LLLLLL");
				// console.log(e);
				this.oldL = e.detail.scrollTop;
				// console.log(this.oldL);
			},
			rightsc(e) {
				// console.log("RRRRRR");
				// console.log(e);
				// 
				this.oldR = e.detail.scrollTop;
				if (this.oldR >= this.Tlist[this.currentL + 1]) {
					// console.log("wang")
					++this.currentL;
					this.scoL = this.scoL + 50;
				}
				else if (this.oldR < this.Tlist[this.currentL]) {
					--this.currentL;
					this.scoL = this.scoL - 50;
				}
				else{
					console.log("wang")
				}
				// this.oldR >= this.Tlist[this.currentL + 1] ? (++this.currentL, this.scoL = this.scoL + 50) : (--this.currentL, this
				// 	.scoL = this.scoL - 50);
				// // console.log(this.Tlist[this.currentL]);
				// console.log(this.Tlist[this.currentL+1]);
				// 

			},
			clickL(index) {
				console.log(index);
				// const query = uni.createSelectorQuery().in(this);
				// query.select("#R-"+index).boundingClientRect(data => {
				//   console.log("得到布局位置信息" + JSON.stringify(data));
				//   console.log("节点离页面顶部的距离为" + data.top);
				//   // this.scoR=data.top;
				// }).exec();
				// console.log(this.Tlist[index])
				this.scoR = this.Tlist[index];
				this.currentL = index;
			},
			Rbottom(e) {
				this.currentL = this.Tlist.length - 1;
			}
		}
	}
</script>

<style>
	page {
		height: 100%;
	}

	.checkL {
		/* background-color: greenyellow; */
		color: #FF6c01;
		border-left: 7rpx solid #fc6d07;
	}
</style>
