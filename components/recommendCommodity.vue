<template>
	<view>
		<view class="recommend-commodity">
			<view class="commodity-list">
				<image src="//img12.360buyimg.com/mobilecms/s372x372_jfs/t1/120709/10/10042/182270/5f3b84dcE996bcdca/b99a95682a13b63f.jpg!q70.dpg.webp"></image>
				<text> 小米（MI） 小米手表color高清大屏智能手表长续航NFC支付多功能防水手表 小米手表color 典雅黑 新款手表 </text>
			</view>
			<view class="commodity-list">
				<image src="//img12.360buyimg.com/mobilecms/s372x372_jfs/t1/120709/10/10042/182270/5f3b84dcE996bcdca/b99a95682a13b63f.jpg!q70.dpg.webp"></image>
				<text> 小米（MI） 小米手表color高清大屏智能手表长续航NFC支付多功能防水手表 小米手表color 典雅黑 新款手表 </text>
			</view>
			<view class="commodity-list">
				<image src="//img12.360buyimg.com/mobilecms/s372x372_jfs/t1/120709/10/10042/182270/5f3b84dcE996bcdca/b99a95682a13b63f.jpg!q70.dpg.webp"></image>
				<text> 小米（MI） 小米手表color高清大屏智能手表长续航NFC支付多功能防水手表 小米手表color 典雅黑 新款手表 </text>
			</view>
			<view class="commodity-list">
				<image src="//img12.360buyimg.com/mobilecms/s372x372_jfs/t1/120709/10/10042/182270/5f3b84dcE996bcdca/b99a95682a13b63f.jpg!q70.dpg.webp"></image>
				<text class="title"> 小米（MI） 小米手表color高清大屏智能手表长续航NFC支付多功能防水手表 小米手表color 典雅黑 新款手表 </text>
				<view>
					<text class="price">$99</text>
					<text class="similarity">找相似</text>
				</view>

			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			};
		}
	}
</script>

<style lang="scss">
	.recommend-commodity {
		width: 100%;
		@include flex-layout(center);
	}

	.commodity-list {
		width: 48%;
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
