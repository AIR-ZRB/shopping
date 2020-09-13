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
				<image :src="item.icon"></image>
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
						icon: "//m.360buyimg.com/mobilecms/s120x120_jfs/t1/125678/35/5947/4868/5efbf28cEbf04a25a/e2bcc411170524f0.png"
					},
					{
						title: "数码电器",
						icon: "//m.360buyimg.com/mobilecms/s120x120_jfs/t1/135931/4/3281/5598/5efbf2c0Edbdc82c7/ed9861b4ddfb9f30.png"
					},
					{
						title: "京东服饰",
						icon: "//m.360buyimg.com/mobilecms/s120x120_jfs/t1/140012/8/1804/3641/5efbf318E38bd5dad/0db99d859ab16ce9.png"
					},
					{
						title: "京东生鲜",
						icon: "//m.360buyimg.com/mobilecms/s120x120_jfs/t1/129215/21/5978/3618/5efbf344Ebec23ae8/59712d986b10bb0a.png"
					},
					{
						title: "京东到家",
						icon: "//m.360buyimg.com/mobilecms/s120x120_jfs/t1/116602/7/11200/3796/5efbf375Ebba41029/f07cc166f368fa05.png"
					},
					{
						title: "充值缴费",
						icon: "//m.360buyimg.com/mobilecms/s120x120_jfs/t1/146390/3/1846/4909/5efbf39aEe5f5f797/300071558a9ab078.png"
					},
					{
						title: "9.9元拼",
						icon: "//m.360buyimg.com/mobilecms/s120x120_jfs/t1/143365/25/1824/3716/5efbf3c0E5175e1fb/88f6227257a29f1d.png"
					},
					{
						title: "领券",
						icon: "//m.360buyimg.com/mobilecms/s120x120_jfs/t1/113589/24/11332/4897/5efbf3feE705d87db/e5c12d5e943266b9.png"
					},
					{
						title: "领金贴",
						icon: "//m.360buyimg.com/mobilecms/s120x120_jfs/t1/131663/33/3380/3674/5efbf50fEf79cf314/af4b57d2383e605d.png"
					},
					{
						title: "PLUS会员",
						icon: "//m.360buyimg.com/mobilecms/s120x120_jfs/t1/123730/37/5924/4189/5efbf567E0a226121/d04df7c74c87cf68.png"
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
			margin-top: 10px;

			@include flex-layout(center,flex-end);

			image {
				width: 46px;
				height: 46px;
				margin-bottom: 5px;
			}
			
			text {
				width: 100%;
				text-align: center;
			}
			
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
