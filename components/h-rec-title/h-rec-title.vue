




<template>
	<!-- 自定义标题组件 -->
	<view class="u-m-t-30 u-m-b-30" style="position: relative;">
		<view class="u-text-center u-font-36 font-weight u-m-b-20" style="text-align: center;">{{title}}</view>
		<view class="u-text-center gray-color u-font-20 bg-white-color u-padding-10 d-flex j-center w-100" style="position: absolute;">
			<text class="px-5" style="background-color: #f8f8f8;letter-spacing: 4rpx;">{{desc}}</text>
		</view>
		<view class="d-flex">
			<view class="u-flex-1" style="background-image: linear-gradient(to right,rgba(27,191,128,0),rgba(27,191,128,1));height: "></view>
		</view>
	</view>
</template>

<script>
	export default {
		
		props:{
			title:{
				type:String,
				default:'优选好物'
			},
			desc:{
				type:String,
				default:'YOU XUAN HAO WU'
			}
		}
		
	}
</script>

<style>

</style>