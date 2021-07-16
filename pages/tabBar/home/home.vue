<template>
	<view>
		<view class="tx-w">
			<view class="search-block">
				<view class="search-ico-wapper">
					<image src="../../../static/tabBar/sousuo.png" class="search-ico" mode=""></image>
				</view>
				<input type="text" value="" placeholder="点击输入搜索内容" class="search-text" maxlength="10" focus />
				<view class="search-ico-wapper1">
				</view>
			</view>
			<view class="tx">
				<swiper indicator-dots circular autoplay interval=3000>
					<swiper-item v-for="(item,index) in swipers" :key="index">
						<image :src="item"></image>
					</swiper-item>
				</swiper>
			</view>
		</view>
		<view class="project">
			<view class="uni-flex uni-row">
				<view class="flex-item fuwu">
					<view>
						<image src="../../../static/tabBar/zhijiayou.png">
					</view>
					<view>美甲</view>
				</view>
				<view class="flex-item fuwu">
					<view>
						<image src="../../../static/tabBar/meibi.png">
					</view>
					<view>纹绣</view>
				</view>
				<view class="flex-item fuwu">
					<view>
						<image src="../../../static/tabBar/jiemaoshua.png">
					</view>
					<view>美睫</view>
				</view>
				<view class="flex-item fuwu">
					<view>
						<image src="../../../static/tabBar/yanbujinghua.png">
					</view>
					<view>美发</view>
				</view>
			</view>
			<view class="uni-flex uni-row">
				<view class="flex-item fuwu">
					<view>
						<image src="../../../static/tabBar/jiemianyi.png">
					</view>
					<view>仪器美容</view>
				</view>
				<view class="flex-item fuwu ">
					<view>
						<image src="../../../static/tabBar/mianshuang.png">
					</view>
					<view>美容SPA</view>
				</view>
				<view class="flex-item fuwu  ">
					<view>
						<image src="../../../static/tabBar/ruye.png">
					</view>
					<view>美体</view>
				</view>
				<view class="flex-item fuwu ">
					<view>
						<image src="../../../static/tabBar/saihong.png">
					</view>
					<view>美妆</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				swipers: []

			}
		},
		onLoad() {
			//模拟ajax获取数据，uni.request({...});注意回调的this指向
			this.swipers = ['../../../static/tabBar/banner.png',
				"../../../static/tabBar/banner.png",
				"../../../static/tabBar/banner.png",
				"../../../static/tabBar/banner.png"
			];

		},
		methods: {

		}
	}
</script>

<style>
	.tx-w {
		padding: 20rpx 20rpx 0;
		height: 350rpx;
		background-image: linear-gradient(#0bc5a3, #00BCD4);
	}

	.search-ico,
	.search-ico-1 {
		width: 40upx;
		height: 40upx;
	}

	.search-text {
		font-size: 14px;
		background-color: #FFFFFF;
		height: 60upx;
		width: 480upx;
	}

	.search-block {
		display: flex;
		flex-direction: row;
		padding-left: 60upx;
		position: relative;
	}

	.search-ico-wapper {
		background-color: #FFFFFF;
		display: flex;
		flex-direction: column;
		justify-content: center;
		padding: 0upx 0upx 0upx 40upx;
		border-bottom-left-radius: 18px;
		border-top-left-radius: 18px;
	}

	.search-ico-wapper1 {
		background-color: #FFFFFF;
		display: flex;
		flex-direction: column;
		justify-content: center;
		padding: 0upx 40upx 0upx 0upx;
		border-bottom-right-radius: 18px;
		border-top-right-radius: 18px;
	}

	.tx {
		margin-top: 20upx;
		text-align: center;
	}

	.tx image {
		height: 100%;
	}

	.project {
		margin-top: 25upx;
		border-bottom: 1upx solid #9e9e9e5c;
	}

	.uni-flex {
		display: flex;
	}

	.flex-item {
		-webkit-box-flex: 1;
		flex: 1;
		display: -webkit-box;
		display: -webkit-flex;
		display: flex;
		-webkit-box-orient: vertical;
		-webkit-box-direction: normal;
		flex-direction: column;
		-webkit-box-align: center;
		align-items: center;
		-webkit-box-pack: center;
		justify-content: center;
	}

	.fuwu {
		width: 33.3%;
		height: 80px;
		text-align: center;
		font-size: 24rpx;
	}

	.fuwu image {
		width: 60rpx;
		height: 60rpx;
	}
</style>
