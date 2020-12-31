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
				<view class="name-ka">开通会员</view>
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
		padding: 20upx 20upx 0;
		background-image: linear-gradient(#0bc5a3, #00BCD4);
	}

	.tx {
		color: #FFFFFF;
		font-weight: bold;
	}

	.tx image {
		float: left;
		width: 140upx;
		height: 140upx;
		border-radius: 50%;
	}

	.name {
		float: left;
		text-align: center;
		margin-top: 60upx;
		margin-left: 20upx;
	}

	.zx {
		clear: both;
	}

	.name-qm {
		margin-top: 30upx;
		padding: 0upx 20upx;
		font-size: 30upx;
		height: 90upx;
		line-height: 90upx;
		background: #333;
		color: #ecc32e;
		border-top-left-radius: 25upx;
		border-top-right-radius: 25upx;
	}

	.name-hei,
	.name-new,
	.name-ka {
		float: left;
	}

	.name-new {
		font-size: small;
		margin-left: 130upx;
	}

	.name-ka {
		margin-top: 15rpx;
		margin-left: 20rpx;
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
</style>
