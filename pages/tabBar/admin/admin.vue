<template>
	<view class="container">
		<view class="tx-w">
			<view class="tx">
				<image class="tx-img" :src="yonghuwx.avatarUrl"></image>
				<view class="name">{{yonghuwx.nickName}} </view>
				<view class="zx"></view>
			</view>
			<view class="name-qm">
				<view class="name-hei">ENJOY黑卡</view>
				<view class="name-new">黑卡权益上新啦</view>
				<view class="name-ka"><text>开通会员</text>
					<image src="../../../static/tabBar/xiangyou1.png">
				</view>
			</view>
		</view>
		<view class="order">
			<view class="my-all">
				<view class="my-order">我的订单</view>
				<image src="../../../static/tabBar/xiangyou2.png">
					<view class="my-view">查看全部 </view>
			</view>
			<view class="uni-flex uni-row">
				<view class="flex-item status">
					<view>
						<image src="../../../static/tabBar/daifukuan.png">
					</view>
					<view>待付款</view>
				</view>
				<view class="flex-item status">
					<view>
						<image src="../../../static/tabBar/daishiyong.png">
					</view>
					<view>待使用</view>
				</view>
				<view class="flex-item status">
					<view>
						<image src="../../../static/tabBar/show.png">
					</view>
					<view>晒台</view>
				</view>
				<view class="flex-item status">
					<view>
						<image src="../../../static/tabBar/wancheng.png">
					</view>
					<view>已完成</view>
				</view>
			</view>
			<view class="jiange"></view>
		</view>
		<view class="order">
			<view class="my-all">
				<view class="my-order">我的服务</view>
			</view>
			<view class="uni-flex uni-row">
				<view class="flex-item fuwu border-right border-bottom">
					<view>
						<image src="../../../static/tabBar/houwuche.png">
					</view>
					<view>购物车</view>
				</view>
				<view class="flex-item fuwu border-right border-bottom">
					<view>
						<image src="../../../static/tabBar/shijian.png">
					</view>
					<view>我的预约</view>
				</view>
				<view class="flex-item fuwu border-right border-bottom">
					<view>
						<image src="../../../static/tabBar/huiyuan2.png">
					</view>
					<view>会员专享</view>
				</view>
				<view class="flex-item fuwu border-bottom">
					<view>
						<image src="../../../static/tabBar/hezuo.png">
					</view>
					<view>免费入驻</view>
				</view>
			</view>
			<view class="uni-flex uni-row">
				<view class="flex-item fuwu border-right border-bottom">
					<view>
						<image src="../../../static/tabBar/dianpu.png">
					</view>
					<view>商家中心</view>
				</view>
				<view class="flex-item fuwu border-right border-bottom">
					<view>
						<image src="../../../static/tabBar/xiaoxi.png">
					</view>
					<view>联系客服</view>
				</view>
				<view class="flex-item fuwu border-right border-bottom">
					<view>
						<image src="../../../static/tabBar/dianhua.png">
					</view>
					<view>一键拨号</view>
				</view>
				<view class="flex-item fuwu border-bottom">
					<view>
						<image src="../../../static/tabBar/caidan.png">
					</view>
					<view>期待更多</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				yonghuwx: []
			}
		},
		onLoad() {
			let that = this;
			uni.login({
				provider: 'weixin',
				success: function(loginRes) {
					// 获取用户信息				
					uni.getUserInfo({
						provider: 'weixin',
						success: function(infoRes) {
							that.yonghuwx = infoRes.userInfo
							console.log(that.yonghuwx)
						}
					});
				}
			});
		},
		methods: {

		}
	}
</script>

<style>
	.tx-w {
		padding: 20rpx 20rpx 0;
		background-image: linear-gradient(#0bc5a3, #00BCD4);
	}

	.tx {
		color: #FFFFFF;
		font-weight: bold;
	}

	.tx image {
		float: left;
		width: 140rpx;
		height: 140rpx;
		border-radius: 50%;
	}

	.name {
		float: left;
		text-align: center;
		margin-top: 60rpx;
		margin-left: 20rpx;
	}

	.zx {
		clear: both;
	}

	.name-qm {
		margin-top: 30rpx;
		padding: 0rpx 20rpx;
		font-size: 30rpx;
		height: 90rpx;
		line-height: 90rpx;
		background: #333;
		color: #ecc32e;
		border-top-left-radius: 25rpx;
		border-top-right-radius: 25rpx;
	}

	.name-hei,
	.name-new,
	.name-ka {
		float: left;
	}

	.name-new {
		font-size: small;
		margin-left: 15%;
	}

	.name-ka {
		margin-top: 15rpx;
		margin-left: 5%;
		padding-left: 20rpx;
		font-size: 28rpx;
		width: 160rpx;
		font-weight: bold;
		height: 60rpx;
		line-height: 60rpx;
		background: #ecc32e;
		color: #333;
		border-radius: 30rpx;

	}

	.name-ka image {
		margin-left: 10rpx;
		width: 25rpx;
		height: 25rpx;
	}

	.my image {
		width: 90rpx;
		height: 90rpx;
	}

	.my-all {
		height: 90rpx;
		margin: 0 25rpx;
		border-bottom: 2rpx solid #9e9e9eb8;
		font-size: 26rpx;
	}

	.my-order {
		float: left;
		margin-top: 30rpx;
	}

	.my-view {
		margin-top: 30rpx;
		color: #9E9E9E;
		float: right;
	}

	.my-all image {
		float: right;
		margin-top: 34rpx;
		width: 30rpx;
		height: 30rpx;
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

	.status {
		width: 33.3%;
		height: 70px;
		text-align: center;
		font-size: 24rpx;
	}

	.status image {
		width: 60rpx;
		height: 60rpx;
	}

	.jiange {
		height: 25rpx;
		background-color: #b2b2b22e;
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

	.border-right {
		border-right: 1px solid #ddd;
	}

	.border-bottom {
		border-bottom: 1px solid #ddd;
	}
</style>
