<template>
	<view>
		<view class="recommend-commodity">
			<view class="recommend">
				<image src="//img11.360buyimg.com/jdphoto/jfs/t1/31601/22/15554/14040/5cc2a86fEbdb1098b/88174b36f85283b6.png"></image>
			</view>
			<view class="commodity-list" v-for="item in _props.commodityDatas">
				<image :src="item.image"></image>
				<text class="title">{{item.title}}</text>
				<view>
					<text class="price">{{item.price}}</text>
					<text class="similarity">找相似</text>
				</view>

			</view>
		</view>
	</view>
</template>

<script>
	export default {
		props: {
			commodityDatas: {
				default () {
					return [{
						title: "小米（MI） 小米手表color高清大屏智能手表长续航NFC支付多功能防水手表 小米手表color 典雅黑 新款手表",
						price: "￥99",
						image: "//img12.360buyimg.com/mobilecms/s372x372_jfs/t1/120709/10/10042/182270/5f3b84dcE996bcdca/b99a95682a13b63f.jpg!q70.dpg.webp"
					}, {
						title: "公牛(BULL) 开关插座 G12系列 10A斜五孔插座二三极宽体插座86型暗装大面板插座G12Z223A 星空灰",
						price: "￥20",
						image: "//img30.360buyimg.com/mobilecms/s372x372_jfs/t1/49644/12/10377/213854/5d774f31Ee2eadac6/5275e2dc068b5924.jpg!q70.dpg.webp"
					}, {
						title: "零食大礼包坚果组合送女友一整箱干果混合巨型女生儿童零食小吃礼包 套餐1-夏威夷组合",
						price: "￥50",
						image: "//img10.360buyimg.com/mobilecms/s372x372_jfs/t1/101377/21/17295/209216/5e86cc55E50fb73b9/336338346b4c7c40.jpg!q70.dpg.webp"
					}, {
						title: "四川蒲江红心猕猴桃大果奇异果新鲜水果15个装单果70-90g",
						price: "￥19",
						image: "//img12.360buyimg.com/mobilecms/s372x372_jfs/t1/143528/15/14744/632761/5fb49bb4Ea57480d6/026af25c4d6cb3a8.jpg!q70.dpg.webp"
					}, ]
				}
			}
		},
		data() {
			return {

			};
		}
	}
</script>

<style lang="scss">
	.recommend-commodity {
		width: 100%;
		@include flex-layout(space-around);
	}

	.recommend {
		margin: 30px 0;

		image {
			height: 40px;
			width: 400px;
			// width: 100%;
			// height: 50px;
		}
	}

	.commodity-list {
		width: 46%;
		margin-bottom: 20px;
		@include flex-layout(center);

		image {
			width: 189px;
			height: 189px;
		}

		text.title {
			display: block;
			font-size: 12px;
			height: 34px;
			overflow: hidden;
			text-overflow: ellipsis;
			margin: 10px 0;
			// word-break: break-all;
		}

		view {
			width: 100%;
			padding: 0 5px;
			@include flex-layout(space-between);

			.price {
				font-size: 14px;
				color: $theme-color;
				font-weight: 700;
			}

			.similarity {
				font-size: 12px;
				padding: 0 5px;
				height: 20px;
				background: #f0f2f5;
				color: gray;
				border-radius: 5px;

			}
		}

	}
</style>
