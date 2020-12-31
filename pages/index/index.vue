<template>
	<view class="content">
		<view class="avatorWrapper">
			<view class="avator">
				<image class="img" src="../../static/logo.png" mode="widthFix"></image>
			</view>
		</view>
		<view class="form">
			<view class="inputWrapper">
				<input class="input" type="text" v-model="username" value="" placeholder="请输入用户名" />
			</view>
			<view class="inputWrapper">
				<input class="input" type="password" v-model="password" value="" placeholder="请输入密码" />
			</view>
			<view class="loginBtn">
				<text v-on:click="submit" class="btnValue">登录</text>
			</view>
			<view class="forgotBtn">
				<text v-on:click="fundPwd">找回密码</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {
			submit: function() {
				if (this.username === undefined) {
					uni.showToast({
						icon: 'none',
						title: '请输入用户名'
					});
					return;
				}
				if (this.password === undefined) {
					uni.showToast({
						icon: 'none',
						title: '请输入密码'
					});
					return;
				}
				if (this.username !== 'admin') {
					uni.showToast({
						icon: 'none',
						title: '用户名不正确'
					});
					return;
				}
				if (this.password !== '123456') {
					uni.showToast({
						icon: 'none',
						title: '密码不正确'
					});
					return;
				}
				if (this.username === 'admin' && this.password === '123456') {
					uni.showToast({
						icon: 'none',
						title: '登录成功'
					});
					uni.navigateTo({
						url:'../tabBar/home/home'
					});

					return;
				}
			},
			fundPwd: function() {
					uni.navigateTo({
						url:'./fundPwd'
					});
			}
		}
	}
</script>

<style>
	.content {
		background: #009688;
		;
		width: 100vw;
		height: 100vh;
	}

	.avatorWrapper {
		height: 30vh;
		width: 100vw;
		display: flex;
		justify-content: center;
		align-items: flex-end;
	}

	.avator {
		width: 200upx;
		height: 200upx;
		overflow: hidden;
	}

	.avator .img {
		width: 100%
	}

	.form {
		padding: 0 100upx;
		margin-top: 80px;
	}

	.inputWrapper {
		width: 100%;
		height: 80upx;
		background: white;
		border-radius: 20px;
		box-sizing: border-box;
		padding: 0 20px;
		margin-top: 25px;
	}

	.inputWrapper .input {
		width: 100%;
		height: 100%;
		text-align: center;
		font-size: 15px;
	}

	.loginBtn {
		width: 100%;
		height: 80upx;
		line-height: 80upx;
		background: #8BC34A;
		border-radius: 50upx;
		margin-top: 50px;
		display: flex;
		justify-content: center;
		align-items: center;

	}

	.loginBtn .btnValue {
		color: white;
		width: 100%;
		height: 100%;
		text-align: center;
	}

	.forgotBtn {
		text-align: center;
		color: #EAF6F9;
		font-size: 15px;
		margin-top: 20px;
	}
</style>
