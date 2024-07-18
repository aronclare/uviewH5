<template>
	
<view>
	<view>
        <u-navbar
            leftText="返回"
            title="iMall" :bgColor="bgColor"
            :safeAreaInsetTop="false"
        >
            <view
                class="u-nav-slot"
                slot="left"
            >
                <u-icon
                    name="arrow-left"
                    size="19"
                ></u-icon>
                <u-line
                    direction="column"
                    :hairline="false"
                    length="16"
                    margin="0 8px"
                ></u-line>
                <u-icon
                    name="home"
                    size="20"
                ></u-icon>
            </view>
        </u-navbar>
		 <u-swiper class="swiper"
		            :list="list3"
		            indicator
		            indicatorMode="line"
		            circular
		    >
			</u-swiper>
			
			<u-search shape="square" :clearabled="true" placeholder="请输入关键字" v-model="keyword"></u-search>
			
	
	</view>
	<view class="u-page">
			<u-list
				@scrolltolower="scrolltolower"
			>
				<u-list-item
					v-for="(item, index) in indexList"
					:key="index"
				>
					<u-cell
						:title="`列表长度-${index + 1}`"
					>
						<u-avatar
							slot="icon"
							shape="square"
							size="35"
							:src="item.url"
							customStyle="margin: -3px 5px -3px 0"
						></u-avatar>
					</u-cell>
				</u-list-item>
			</u-list>
	</view>
	
	<view>
		<button type="default" @click="clickeHandle">泡我</button>
	</view>
	<view>
			<u-tabbar
			:placeholder="false"
			:value="value3"
			@change="name => value3 = name"
			:fixed="false"
			:safeAreaInsetBottom="false"
			>
				<u-tabbar-item text="首页" icon="home" name="home"></u-tabbar-item>
				<u-tabbar-item text="放映厅" icon="photo" name="photo" ></u-tabbar-item>
				<u-tabbar-item text="直播" icon="play-right" name="play-right"></u-tabbar-item>
				<u-tabbar-item text="我的" name="account" icon="account" ></u-tabbar-item>
			</u-tabbar>
	</view>
		
</view>
</template>


<script>
	export default {
		data() {
			return {
				bgColor: '#001f3',
				list3: [
				                    'https://cdn.uviewui.com/uview/swiper/swiper3.png',
				                    'https://cdn.uviewui.com/uview/swiper/swiper2.png',
				                    'https://cdn.uviewui.com/uview/swiper/swiper1.png',
				                ],
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
								
							
			}
		},
		onLoad() {
					this.loadmore()
				},
				
				
		methods: {
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
					clickeHandle(){
						console.log('我被点击了');
						console.log('it`s OK?');
					}
		},
	}
</script>

<style lang="scss">
	.swiper{
		margin-top: 10rpx;
	}
	
</style>
