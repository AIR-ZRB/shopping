<template>
	<view class="product">
		<view class="product-image">
			<image :src="product.image"></image>
		</view>
		<view class="product-message">
			<text class="price">￥{{product.price}}</text>
			<view>
				<text class="title">{{product.title}}</text>
				<text class="warn">【关注店铺领券下单】【本店为小米品牌授权店铺，全部商品自营同款放心选购】【一年质保，售后无忧】进店购买 </text>
			</view>
		</view>

		<view class="discounts">
			<h3>优惠</h3>
			<text>体验卡免费领，超大流量任性用</text>
		</view>

		<view class="delivery">
			<view>
				<h3 class="">已选</h3>
				<text>小米手表color 雅典黑，新款手表，1个</text>
			</view>
			<view>
				<h3>送至</h3>
				<text>北京朝阳区三环到四环之间</text>
			</view>
			<view>
				<h3>运费</h3>
				<text>在线支付免运费</text>
			</view>
		</view>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				product: {
					price: "699",
					title: "小米（MI） 小米手表color高清大屏智能手表长续航NFC支付多功能防水手表 小米手表color 典雅黑 新款手表",
					image: "//m.360buyimg.com/mobilecms/s750x750_jfs/t1/120709/10/10042/182270/5f3b84dcE996bcdca/b99a95682a13b63f.jpg!q80.dpg.webp"
				}
			}
		},
		methods: {

		}
	}
</script>

<style lang="scss" scoped>
	.product {
		background: #F2F2F2;
		height: 100%;
	}

	.product-image {
		image {
			width: 100%;
			height: 375px;
		}
	}

	.product-message {
		background-color: #FFFFFF;
		padding: 20px;
		border-radius: 10px;

		.price {
			font-size: 24px;
			color: $theme-color;
			font-weight: 700;

		}

		.title {
			font-weight: 700;
			font-size: 18px;
			display: block;
			margin: 20px 0;
		}

		.warn {
			font-size: 12px;
			color: gray;
		}
	}

	.discounts {
		
		margin: 20px 0;
		padding: 10px 20px;
		background: #FFFFFF;
		border-radius: 10px;
		@include flex-layout(flex-start,center)
		text {
			margin-left: 20px;
			font-size: 12px;
		}
	}

	.delivery {
		background: #FFFFFF;
		padding: 0 20px;
		border-radius: 10px;

		view {
			padding: 20px 0;
			@include flex-layout(flex-start,center);
			text {
				font-size: 12px;
				margin-left: 20px;
			}
		}
	}
</style>
