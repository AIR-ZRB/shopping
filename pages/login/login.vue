<template>
	<view class="login">

		<view class="login-box">
			<text class="login-title">LOGIN</text>
			<view class="login-input">
				<text>Phone</text>
				<input class="uni-input" placeholder="请输入电话号码" />
				<text>Password</text>
				<input class="uni-input" placeholder="请输入密码" type="password" />
				<text class="forget">Forget Password?</text>
			</view>
			<button>LOGIN</button>
		</view>

	</view>
</template>

<script>
	export default {

	}
</script>

<style lang="scss" scoped>
	.login {
		width: 100%;
		height: 100%;
		background: #2A3B71;
		overflow: hidden;
		position: relative;

		&:after {
			content: "";
			position: absolute;
			bottom: 0;
			left: 0;
			width: 0;
			height: 0;
			border-top: 50px solid transparent;
			border-right: 1000px solid transparent;
			border-bottom: 150px solid #fff;

		}
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
				color: #8193B9;
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
