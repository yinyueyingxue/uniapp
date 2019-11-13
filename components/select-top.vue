<template>
	<view class="d-flex a-center" style="justify-content:space-around ;font-size: 20rpx;height:90rpx ;border: 2rpx #f1f1f1 solid;">
		<block v-for="(item,index) in resdata" :key="index">
			<view class="d-flex s-color" v-if="selectIndex" @tap="select(item,index)">{{item.title}}
				<view v-if="item.cir" class="d-flex flex-column" style="justify-content:space-around;margin-left:10rpx;">
					<triUp></triUp>
					<triDown></triDown>
				</view>
			</view>
			<view class="d-flex" v-else @tap="select(item,index)">{{item.title}}
				<view v-if="item.cir" class="d-flex flex-column" style="justify-content:space-around;margin-left:10rpx;">
					<triUp></triUp>
					<triDown></triDown>
				</view>
			</view>
		</block>
	</view>
</template>
<script>
	import triUp from "@/components/css-icon/tri-up.vue"
	import triDown from "@/components/css-icon/tri-down.vue"
	export default {
		props: {
			resdata: Array,
		},
		components: {
			triUp,
			triDown,
		},
		data() {
			return {
				selectIndex: true
			}
		},
		methods: {
			select(item, index) {
				this.selectIndex = !this.selectIndex;
				// console.log(item);
				// console.log("click！" + this.selectIndex + "__" + "__" + index);
				if (item.title == "筛选") {
					this.$emit("isshow",true)
				}
			}
		}
	}
</script>

<style>
	.s-color {
		color: #ff6900;
	}
</style>
