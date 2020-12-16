<template>
	<view class="product">
		<view class="product-message">
			<text class="price">￥{{product.price}}</text>
			<view>
				<text class="title">{{product.title}}</text>
				<text class="warn">【关注店铺领券下单】【本店为小米品牌授权店铺，全部商品自营同款放心选购】【一年质保，售后无忧】进店购买 </text>
			</view>
		</view>

		<view class="discounts">
			<text>优惠</text>
			<text>体验卡免费领，超大流量任性用</text>
		</view>

		<view class="delivery">
			<view>
				<text>已选</text>
			</view>
			<view>
				<text>送至</text>
			</view>
			<view><text>运费</text></view>
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

	.product-message {
		background-color: #FFFFFF;
		padding: 20px;

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
		font-size: 14px;
		font-weight: 700;
		margin: 20px 0;
		padding: 10px 20px;
		background: #FFFFFF;
	}

	.delivery {
		background: #FFFFFF;
		padding: 10px 20px;
		view {
			padding: 10px 0;
			font-weight: 700;
		}
	}
</style>
