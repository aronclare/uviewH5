<template>
	<view class="px-20" style="padding-top: 70rpx;">
		<view v-for="(i,index) in 20" class="shadow u-border-radius d-flex u-padding-10 a-center" style="height: 200rpx;">
			<image src="../../static/logo.png" mode="" class="flex-shrink img-160 mx-20 u-border-radius"></image>
			<view class="d-flex u-flex-column j-sb h-100 u-line-1">
				<view class="u-m-t-10">
					<view class="u-line-1 u-font-26">APP外卖订餐会员管理</view>
					<view class="u-line-1 u-font-32 gray-color">超级外卖订餐会员管理</view>
				</view>
				<view class="d-flex j-sb w-100">
					<view class="d-flex a-end">
						<h-pprice></h-pprice>
						<h-oprice></h-oprice>
					</view>
					<view>
						<u-button type="success" size="mini">立刻购买</u-button>
						
					</view>
					
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"h-goods-listrow",
		data() {
			return {
				
			};
		}
	}
</script>

<style>

</style>