<template>
	<view class="product">

		<navigator url="/" open-type="navigate">
			<view class="product-ctrl">
			</view>
		</navigator>
		<view class="product-image">
			<image :src="product.image"></image>
		</view>
		<view class="product-message">
			<text class="price">{{product.price}}</text>
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
				<text>雅典黑，新款商品，1个</text>
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

		},
		created() {
			const that = this;
			// console.log(this.$route.query);
			const id = that.$route.query.id;
			console.log()
			uni.request({
				url: `http://localhost:4000/product?id=${id}`,
				method: 'GET',
				success: function(res) {
					that.product = res.data[0];
				}
			})
		}
	}
</script>

<style lang="scss" scoped>
	.product {
		background: #F2F2F2;
		height: 100%;
	}

	navigator {
		// width: 100%;
		padding: 10px;
		// @include flex-layout(space-between);
		position: fixed;
		top: 0;
		left: 0;
		z-index: 2;
	}

	.product-ctrl {
		// display: block;
		width: 26px;
		height: 26px;
		padding: 5px;
		background-color: #666;
		background-image: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADQAAAA0CAMAAADypuvZAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAzUExURUdwTP///////////////////////////////////////////////////////////////8/RimEAAAAQdFJOUwDudZkPVzL7Id+xQr+K0WiwaJlcAAABMUlEQVRIx+1V27KDIAyUSwgBRP7/a0u00ypaQmfOmfaheXBAs3E3CWGafvYd5gwhknFvQLwpdzN+EGK1Yn9EfiptRzBA7BwqMxd4RSCLSeyY47aLmXepL80a5qSW55uFqaLpcFzF4HzwsPMaR7+AbFzCKV8+7BlffKJ4GY4uwwkkLomvcktPrl3rvUvRUGKbYjgcK+FWdtxiL3U11ixW1/h3hvNwW9ZWnj9x6Lz27ztRIRnUOtVcyqDW6QMgnwIczxOE5AUQ9yUmDdFb6yPoxD1mBBBgORmCpMlvwZ+I9KhONxEWTCKFqCiZvcAvSPm/g3AMhE0DF/EucqXp8jopxXM813l5HDT117GPiVVCM7IyD9AOQ8cjOLdHWRXR1PluyBImX40RCISvAEgBpp/9id0AtW0Z2VD6WC0AAAAASUVORK5CYII=);
		background-repeat: no-repeat;
		background-position: 50%;
		background-size: 26px 26px;
		border-radius: 50%;
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

		@include flex-layout(flex-start, center) text {
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
			@include flex-layout(flex-start, center);

			text {
				font-size: 12px;
				margin-left: 20px;
			}
		}
	}
</style>
