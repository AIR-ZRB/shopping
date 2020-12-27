<template>
	<view class="login">

		<view class="login-box">
			<text class="login-title">青商城</text>
			<view class="login-input">
				<text>Phone</text>
				<input class="uni-input" placeholder="请输入电话号码" v-model.trim="phoneNumber" />
				<text>Password</text>
				<input class="uni-input" placeholder="请输入密码" type="password" v-model.trim="password" />
				<text class="forget">Forget Password?</text>
			</view>
			<button @click="login">LOGIN</button>
		</view>
		<message text="登录成功" :show="isShow"/>
	</view>
</template>

<script>
	import message from "@/components/message.vue";
	export default {
		data() {
			return {
				phoneNumber: "admin",
				password: "admin",
				isShow: false
			}
		},
		components: {
			message
		},
		methods: {
			login() {
				if (this.phoneNumber === "admin" && this.password === "admin") {
					localStorage.setItem("login", "true");
					console.log("伪登录Success");
					this.isShow = true;

					uni.navigateBack({ //uni.navigateTo跳转的返回，默认1为返回上一级
						delta: 1
					});
				}
			}
		}
	}
</script>

<style lang="scss" scoped>
	.login {
		width: 100%;
		height: 100%;
		background: #FAB3B3;
		// background-image: linear-gradient(to top,#F20300, #FFCABA);
		overflow: hidden;
		position: relative;

		&:after {
			content: "";
			position: absolute;
			bottom: 0;
			left: 0;
			width: 0;
			height: 0;

		}
	}

	.login-title {
		width: 100%;
		display: block;
		text-align: center;
	}

	.login-box {
		margin-top: 30%;
		padding: 0 20px;
		color: #fff;

		.login-title {
			font-size: 30px;
			font-weight: 700;
			letter-spacing: 2px;
		}


		.login-input {
			margin-top: 30px;

			text {
				// color: #8193B9;
				color: #FFF;
				letter-spacing: 1px;
			}

			.input-placeholder {
				color: #fff;
			}

			.forget {
				display: block;
				font-size: 12px;
				font-weight: 700;
				text-align: right;
			}

			.uni-input {
				margin-bottom: 20px;
				padding: 10px 0;
				border-bottom: 1px solid #ccc;
			}
		}

		button {
			margin: 40px auto;
			background-color: transparent;
			border: 1px solid #fff;
			width: 40%;
			padding: 0 20px;
			color: #fff;
			letter-spacing: 1px;
		}


	}
</style>
