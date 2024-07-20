<template>

	<view>
		<view>
			<!-- 导航栏 -->
			<u-navbar leftText="返回" title="iMall" :bgColor="bgColor">
				<view class="u-nav-slot" slot="left">
					<u-icon name="arrow-left" size="19"></u-icon>
					<u-line direction="column" :hairline="false" length="16" margin="0 8px"></u-line>
					<u-icon name="home" size="20"></u-icon>
				</view>
			</u-navbar>
			<!-- 滚动轮播图 -->
			<u-swiper class="swiper" style="margin-top: 44px;" :list="list3" indicator indicatorMode="line" circular
				height="130" margin="10px">
			</u-swiper>
			<!-- 滚动通知 -->
			<u-notice-bar :text="text1" speed="150"></u-notice-bar>
			<!-- 搜索框 -->
			<u-search class="pad20" shape="square" :clearabled="true" placeholder="请输入搜索关键词"
				v-model="keyword"></u-search>
			<!-- 分类宫格-->
			<u-grid :border="false" col="4" @click="click">
				<u-grid-item v-for="(baseListItem,baseListIndex) in baseList" :key="baseListIndex">
					<u-icon :customStyle="{paddingTop:20+'rpx'}" :name="baseListItem.name" :size="22"></u-icon>
					<text class="grid-text">{{baseListItem.title}}</text>
				</u-grid-item>
			</u-grid>
			<u-toast ref="uToast" />

		</view>
		<!-- 二级分类部分 -->
		<view class="goodsList" style="height: 375rpx;width: 100%; background-color: #1BBF80;">
			<view class="white-color d-flex u-flex-column u-m-t-30">
				<text class="u-font-26 u-p-b" style="border-bottom: 3rpx solid #FFFFFF;">专属定制 优质服务</text>
				<text class="u-font-36 font-weight ">APP定制开发</text>
				<image src="https://cdn.uviewui.com/uview/swiper/swiper3.png" style="width: 30%;height: 60rpx;"></image>
			</view>
			<view class="bg-white-color shadow u-border-radius d-flex flex-wrap"
				style="width: 710rpx; height: 350rpx; margin: 0rpx auto 30rpx;">

				<view v-for="i in 4"
					style="width: 350rpx;height: 175rpx; border: 1rpx solid white; background-color: yellow;"></view>
			</view>
		</view>
		<!-- 商品列表部分 -->
		<!-- <view class="px-20 d-flex j-sb flex-wrap u-m-t-40">
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
		</view> -->
		<h-goods-list></h-goods-list>

		<h-rec-title title="猜你喜欢" desc="CAI NI XI HUAN"></h-rec-title>


		<!-- 自定义标题组件 -->
		<!-- <view class="u-m-t-30 u-m-b-30" style="position: relative;">
			<view class="u-text-center u-font-36 font-weight u-m-b-20" style="text-align: center;">优选好物</view>
			<view class="u-text-center gray-color u-font-20 bg-white-color u-padding-10 d-flex j-center w-100" style="position: absolute;">
				<text class="px-5" style="background-color: #f8f8f8;letter-spacing: 4rpx;">YOU XUAN HAO WU</text>
			</view>
			<view class="d-flex">
				<view class="u-flex-1" style="background-image: linear-gradient(to right,rgba(27,191,128,0),rgba(27,191,128,1));height: "></view>
			</view>
		</view> -->
		<!-- 间隔槽 -->
		<u-gap height="50" bgColor="#f8f8f8"></u-gap>
		<!-- 商品列表样式2 -->
		<!-- <view class="px-20" style="padding-top: 70rpx;">
			<view v-for="(i,index) in 8" class="shadow u-border-radius d-flex u-padding-10 a-center" style="height: 200rpx;">
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
		</view> -->
		<h-goods-listrow></h-goods-listrow>

		<!-- 返回顶部 -->
		<u-back-top :scroll-top="scrollTop" :icon-style="iconStyle"></u-back-top>
		<!-- 上拉加载更多 -->
		<u-loadmore :status="status" :loading-text="loadingText"/>


		<view class="" style="width: 100%; height: 200rpx;"></view>



		<!-- <view class="u-page">
			<u-list @scrolltolower="scrolltolower">
				<u-list-item v-for="(item, index) in indexList" :key="index">
					<u-cell :title="`列表长度-${index + 1}`">
						<u-avatar slot="icon" shape="square" size="35" :src="item.url"
							customStyle="margin: -3px 5px -3px 0"></u-avatar>
					</u-cell>
				</u-list-item>
			</u-list>
		</view> -->

		<view>
			<button type="default" @click="clickeHandle">点我</button>
		</view>
		<view>
			<u-tabbar :placeholder="false" :value="value3" @change="name => value3 = name" :fixed="false"
				:safeAreaInsetBottom="false">
				<u-tabbar-item text="首页" icon="home" name="home"></u-tabbar-item>
				<u-tabbar-item text="放映厅" icon="photo" name="photo"></u-tabbar-item>
				<u-tabbar-item text="直播" icon="play-right" name="play-right"></u-tabbar-item>
				<u-tabbar-item text="我的" name="account" icon="account"></u-tabbar-item>
			</u-tabbar>
		</view>

	</view>
</template>


<script>
	/* 导入轮播图swiper数据 */
	import banner from "@/common/data/swiper.js"
	/* 导入分类数据 */
	import cateList from "@/common/data/cateList.js"

	export default {
		data() {
			return {
				bgColor: '#001f3',
				list3: banner,
				keyword: '请输入关键字搜索',
				value3: 'play-right',
				indexList: [],
				urls: [
					'https://cdn.uviewui.com/uview/album/1.jpg',
					'https://cdn.uviewui.com/uview/album/2.jpg',
					'https://cdn.uviewui.com/uview/album/3.jpg',
					'https://cdn.uviewui.com/uview/album/4.jpg',
					'https://cdn.uviewui.com/uview/album/5.jpg',
					'https://cdn.uviewui.com/uview/album/6.jpg',
					'https://cdn.uviewui.com/uview/album/7.jpg',
					'https://cdn.uviewui.com/uview/album/8.jpg',
					'https://cdn.uviewui.com/uview/album/9.jpg',
					'https://cdn.uviewui.com/uview/album/10.jpg',
				],
				text1: 'uView UI众多组件覆盖开发过程的各个需求，组件功能丰富，多端兼容。让您快速集成，开箱即用',
				baseList: cateList,
				scrollTop: 0, //返回顶部监听滚动条
				iconStyle: { //返回顶部样式
					fontSize: '32rpx',
					color: '#1bbf80'
				},
				//加载更多
				status:'loadmore',
				iconType:'flower',
				loadText:{
					loadmore:'轻轻上拉',
					loading:'努力加载中',
					nomore:'实在没有了'
				}

			}
		},

		onPageScroll(e) { //返回顶部监听滚动条
			this.scrollTop = e.scrollTop;
		},
		onReachBottom() {  //上拉加载更多
		this.status = 'loading',
		setTimeout(()=>{
			this.addGoods()
		},3000)
		},
		onLoad() {
			this.loadmore()
		},


		methods: {
			
			addGoods(){
				for(let i = 0;i<6;i++){
					let index =this.$u.random(0,this.goodsList.length-1)
					let item = this.goodsList[index]
					this.goodsList.push(item)
					
				}
				
			},
			
			
			scrolltolower() {
				this.loadmore()
			},
			loadmore() {
				for (let i = 0; i < 10; i++) {
					this.indexList.push({
						url: this.urls[uni.$u.random(0, this.urls.length - 1)]
					})
				}
			},
			click(name) {
				this.$refs.uToast.success(`点击了第${name+1}个`)
			},
			clickeHandle() {
				console.log('我被点击了');
				console.log('it`s OK?');
			}
		},
	}
</script>

<style lang="scss">
	.grid-text {
		font-size: 14px;
		color: #909399;
		padding: 10rpx 0 20rpx 0rpx;
		/* #ifndef APP-PLUS */
		box-sizing: border-box;
		/* #endif */
	}

	.pad20 {
		padding: 10px 12px 10px 12px;
	}
</style>