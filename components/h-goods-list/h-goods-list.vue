<template>
	<!-- 商品列表部分 -->
	<view class="px-20 d-flex j-sb flex-wrap u-m-t-40">
		<view v-for="(i,index) in 4" class="shadow u-m-b-30" style="border-top-left-radius: 10rpx; border-top-right-radius: 10rpx; width: 345rpx;">
			<image src="../../static/logo.png" class="img-345" style="border-top-left-radius: 10rpx; border-top-right-radius: 10rpx;"></image>
			<view class="px-10">
				<view class="u-line-1 u-font-weight black-color my-10">App定制开发交友直播本地生活</view>
				<view class="u-line-1 u-font-24 gray-color">App定制开发交友直播本地生活</view>
				
			</view>
			<view class="d-flex a-end">
				<view class="main-color u-m-r-15">
					<text class="font-weight u-font-26">￥</text>
					<text class="font-weight u-font-36">99</text>
				</view>
				<view class="line-throught gray-color u-font-26">
					199
				</view>
				
			</view>
			<u-icon name="shopping-cart" color="#1bbf80" size="36"></u-icon>
		</view>
	</view>
</template>

<script>

	export default {
		
		props:{
		
		}
		
	}
</script>

<style>

</style>
