<template>
	<view class="content">

		<view class="search">
			<text>Menu</text>
			<input type="text" :value="searchValue">
			<text>登录</text>
		</view>

		<swiper class="banners" :indicator-dots="true" :autoplay="true" :interval="2000" :duration="500">
			<swiper-item v-for="item in banner" :key="item">
				<image :src="'../../static/images/'+item"></image>
			</swiper-item>
		</swiper>

		<view class="classify">
			<view v-for="item in classify" :key="item.title" class="classify-item">
				<text>{{item.title}}</text>
			</view>
		</view>

		<view class="second-skill">
			<text>京东秒杀 10点场</text>
		</view>

		<view class="new-member">
			<image src="../../static/images/new-member-welfare1.jpg"></image>
			<image src="../../static/images/new-member-welfare2.jpg"></image>
		</view>







	</view>
</template>

<script>
	export default {
		data() {
			return {
				searchValue: "",
				banner: ["banner1.jpg", "banner2.jpg", "banner3.jpg", "banner4.jpg"],
				classify: [{
						title: "京东超市",
						icon: ""
					},
					{
						title: "数码电器",
						icon: ""
					},
					{
						title: "京东服饰",
						icon: ""
					},
					{
						title: "京东生鲜",
						icon: ""
					},
					{
						title: "京东到家",
						icon: ""
					},
					{
						title: "充值缴费",
						icon: ""
					},
					{
						title: "9.9元拼",
						icon: ""
					},
					{
						title: "领券",
						icon: ""
					},
					{
						title: "领金贴",
						icon: ""
					},
					{
						title: "PLUS会员",
						icon: ""
					},

				]
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style lang="scss">
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.search {
		height: 50px;
		width: 100%;
		background: #C82519;
		display: flex;
		justify-content: space-around;
		align-items: center;

		text {
			font-size: 16px;
			color: white;
		}

		input {
			$input-height: 30px;
			width: 60%;
			height: $input-height;
			background-color: white;
			padding: 0 10px;
			font-size: 14px;
			border-radius: $input-height / 2;
			border: none;
		}
	}

	.banners {
		height: 300rpx;
		width: 100%;

		image {
			width: 100%;
			height: 100%;
		}
	}

	.classify {
		width: 100%;

		.classify-item {
			width: 20%;
			height: 70px;
			float: left;
			font-size: 14px;
			display: flex;
			align-items: flex-end;
			justify-content: center;
		}
	}

	.second-skill {
		margin-top: 30rpx;
		width: 100%;
		height: 300rpx;
		background-color: gray;
	}

	.new-member {
		margin-top: 30rpx;
		width: 100%;

		image {
			width: 50%;
			height: 200rpx;
		}
	}
</style>
