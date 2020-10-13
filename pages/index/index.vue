<template>
	<view class="content">

		<view class="search">
			<text><image src="../../static/icon/menu.png" mode=""></image></text>
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
			<text class="kill-time">
				京东秒杀
				<text class="time">
					<text class="tiem-bucket">
						{{nowSession}}点场
					</text>
					<text class="count-down">
						{{countDown}}
					</text>
				</text>
			</text>
			<view class="kill-commodity">
				<view v-for="item in secondsKill" :key="item.coommodityId">
					<image :src="item.image"></image>
					<text>￥{{item.afterPrice}}</text>
					<text>￥{{item.beforePrice}}</text>
				</view>
			</view>


		</view>

		<view class="new-member">
			<image src="//m.360buyimg.com/mobilecms/s376x240_jfs/t1/49601/16/12206/115887/5d91b4d5E34709952/aba2bcb4855e6e52.png!q70.jpg.dpg"></image>
			<image src="//m.360buyimg.com/mobilecms/s376x240_jfs/t1/32449/33/15631/174497/5cc2d86bE0289110c/9c53e25651659d43.png!q70.jpg.dpg"></image>
			<image src="//m.360buyimg.com/mobilecms/s750x100_jfs/t1/111655/4/10853/142323/5ef22455Eb86abfc1/2bf122bb2e87d6e3.png.webp"></image>
		</view>


	</view>
</template>

<script>
	export default {
		data() {
			return {
				countDown: "00:00:00",
				nowSession: "",
				searchValue: "",
				banner: ["banner1.jpg", "banner2.jpg", "banner3.jpg", "banner4.jpg"],
				secondsKill: [{
						coommodityId: 1,
						beforePrice: 299,
						afterPrice: 248,
						image: "https://wqimg.jd.com/imgproxy/n7/s150x150_jfs/t1/126478/6/13805/50136/5f71b27bEdcf24eff/021581a888ca8f11.jpg.dpg"
					},
					{
						coommodityId: 2,
						beforePrice: 3200,
						afterPrice: 2499,
						image: "https://wqimg.jd.com/imgproxy/n7/s150x150_jfs/t1/150266/7/10300/144621/5f7fc501E00a498e2/367895e25cbd4a38.jpg.dpg"
					},
					{
						coommodityId: 3,
						beforePrice: 9288,
						afterPrice: 7000,
						image: "https://wqimg.jd.com/imgproxy/n7/s150x150_jfs/t1/148119/13/10361/191808/5f817c2aE7c81e395/4c5d33239f6db5c8.jpg.dpg"
					},
					{
						coommodityId: 4,
						beforePrice: 354,
						afterPrice: 318,
						image: "https://wqimg.jd.com/imgproxy/n7/s150x150_jfs/t1/130148/35/12007/66224/5f80259cEa8831e42/4b20c7d4b3f411cc.jpg.dpg"
					},
					{
						coommodityId: 5,
						beforePrice: 600,
						afterPrice: 411,
						image: "https://wqimg.jd.com/imgproxy/n7/s150x150_jfs/t1/136008/23/11139/101039/5f7430adE46006433/83a955f70cedbc88.jpg.dpg"
					},
					{
						coommodityId: 6,
						beforePrice: 128,
						afterPrice: 88,
						image: "https://wqimg.jd.com/imgproxy/n7/s150x150_jfs/t1/129089/13/14337/127308/5f7fdcb1Eb135e164/3924fd40c72e677d.jpg.dpg"

					},

				],
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
		methods: {
			countDownTime() {
				setInterval(() => {
					// 获取偶数场次
					let session = new Date().getHours();
					(session + 2) % 2 === 0 ? session += 2 : session += 1;
					this.nowSession = session;


					let year = new Date().getFullYear();
					let month = new Date().getMonth() + 1;
					let today = new Date().getDate();


					// 获取倒计时
					let nowTime = +new Date();
					let endTime = +new Date(`${year},${month},${today} ${session}:0:0`);
					let remainTime = parseInt((endTime - nowTime) / 1000);
					let hours = parseInt(remainTime / 3600 % 24);
					let minute = parseInt(remainTime / 60 % 60);
					let seconds = remainTime % 60

					this.countDown = `${hours}:${minute}:${seconds}`
				}, 1000)
			}
		},
		created() {
			this.countDownTime()
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
		background: $theme-color;
		display: flex;
		justify-content: space-around;
		align-items: center;

		text {
			font-size: 14px;
			color: white;
		}

		input {
			$input-height: 30px;
			width: 60%;
			height: $input-height;
			background-color: white;
			padding: 0 14px;
			font-size: 14px;
			border-radius: $input-height / 2;
			border: none;
		}
		image {
			width: 24px;
			height: 24px;
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
			margin-top: 20rpx;

			@include flex-layout(center, flex-end);

			image {
				@include square-size(80rpx, 58px);
				margin-bottom: 10rpx;
			}

			text {
				width: 100%;
				text-align: center;
				font-size: 12px;
			}

		}
	}

	.second-skill {
		margin-top: 30rpx;
		width: 100%;
		height: 320rpx;
		overflow-x: scroll;


		.kill-time {
			display: block;
			line-height: 33px;
			padding: 5px 10px;
			font-size: 14px;

			.time {
				font-size: 12px;
				margin-left: 10px;
				border: 1px solid $theme-color;
				color: #fff;
				border-radius: 12px;
				padding: 0 10px 0 0;
				font-weight: 700;

				.tiem-bucket {
					font-size: 12px;
					background: $theme-color;
					border-radius: 12px;
					padding: 0 6px;
				}

				.count-down {
					font-size: 12px;
					color: $theme-color;
					padding: 0 10px;
				}
			}
		}

		.kill-commodity {
			width: 120%;
			@include flex-layout(space-between, center);

			view {
				padding: 0 5px;

				image {
					@include square-size(120rpx, 144px);
					margin-bottom: 10px;
				}

				text {
					display: block;
					text-align: center;
					font-size: 12px;
					font-weight: 700;
					color: $theme-color;

					&:last-child {
						color: #999;
						text-decoration: line-through;
					}
				}
			}
		}

	}

	.new-member {
		margin-top: 30rpx;
		width: 100%;

		image {
			width: 50%;
			height: 200rpx;
			@include box-size(50%, 210rpx, 50%, 178px);

			&:last-child {
				width: 100%;
				height: 50px;
				margin-top: 10px;
			}
		}
	}
</style>
