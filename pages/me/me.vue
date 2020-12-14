<template>
	<view class="my">
		<un-navigation>
			<text>我的</text>
		</un-navigation>
		
		 
		<view class="author">
			<view class="author-picture">
				{{authorName}}
			</view>

			<view class="user-message">
				<text class="username">青空</text>
				<text>青享值：1221</text>
				<text>小白信用：1331</text>
			</view>

			<view class="commodity-status">
				<view v-for="item in commodityStatus" :key="item.text">
					<text class="count">{{item.count}}</text>
					<text class="description">{{item.text}}</text>
				</view>
			</view>
		</view>

		<view class="order-messsage">
			<shoppingItems v-for="item in orderMessage" :key="item.text" :item="item" />
		</view>

		<view class="discounts">
			<shoppingItems v-for="item in discounts" :key="item.text" :item="item" />
		</view>

		<view class="serve">
			<text class="serve-title">工具与服务</text>
			<shoppingItems v-for="item in serve" :key="item.text" :item="item" />
		</view>


	</view>
</template>

<script>
	import shoppingItems from "./shopping-items.vue";
	import unNavigation from "../../components/navigation.vue";
	export default {
		data() {
			return {
				username: "青空",
				commodityStatus: [{
						text: "商品收藏",
						count: 1
					},
					{
						text: "店铺收藏",
						count: 2
					},
					{
						text: "我的足迹",
						count: 3
					},
				],
				orderMessage: [{
						icon: "https://img12.360buyimg.com/img/s60x60_jfs/t1/125209/17/7530/933/5f16524bE43b4a5f7/71971b102d1fcbc5.png",
						text: "待付款"
					},
					{
						icon: "https://img12.360buyimg.com/img/s120x120_jfs/t1/123660/33/7797/4674/5f1804aeE308173db/b392f9ce63eb8490.png",
						text: "待收货"
					},
					{
						icon: "https://img12.360buyimg.com/img/s60x60_jfs/t1/120478/38/7592/2211/5f165256E02190e99/1491d4cb340074bb.png",
						text: "退换/售后"
					},
					{
						icon: "https://img12.360buyimg.com/img/s60x60_jfs/t1/145618/2/3439/692/5f16525eE30cd2db1/3ab434ec2686a256.png",
						text: "全部订单"
					},
				],
				discounts: [{
						count: 0,
						text: "优惠券"
					},
					{
						count: 280,
						text: "青豆"
					},
					{
						count: 10,
						text: "红包"
					},
					{
						count: 1000,
						text: "白条"
					},

				],
				serve: [{
						icon: "http://img12.360buyimg.com/img/s70x70_jfs/t1/135809/4/7014/5528/5f35369dE8aff3fab/f4b952a87ea33ae4.png.webp",
						text: "客户服务"
					},
					{
						icon: "//img12.360buyimg.com/img/s70x70_jfs/t1/143427/38/5400/4413/5f350384Edba4458b/bfcb210d2110a7d8.png.webp",
						text: "我的预约"
					}, {
						icon: "//img12.360buyimg.com/img/s70x70_jfs/t1/126073/34/9502/6741/5f350800Ee00c0d35/43485badf62439e9.png.webp",
						text: "高价回收"
					}, {
						icon: "//img12.360buyimg.com/img/s70x70_jfs/t1/133114/37/6851/4896/5f350a40Ee99a608e/b273c57d0960f507.png.webp",
						text: "青火车票"
					}, {
						icon: "//img12.360buyimg.com/img/s70x70_jfs/t1/132818/33/6802/4632/5f350a87E52a6f93d/82551e3481c8648b.png.webp",
						text: "应用推荐"
					}, {
						icon: "//img12.360buyimg.com/img/s140x140_jfs/t1/117037/39/16019/18915/5f45fff5Ef548450b/5a850b15881714e8.png.webp",
						text: "青机票"
					}, {
						icon: "//img12.360buyimg.com/img/s70x70_jfs/t1/133985/31/6910/4334/5f350addE170daf0e/5a47542d98d229d0.png.webp",
						text: "青酒店"
					}, {
						icon: "//img12.360buyimg.com/img/s70x70_jfs/t1/112188/32/14787/4956/5f3509edE376c2ddb/d716c6822cafa2b6.png.webp",
						text: "闲置换钱"
					},
				]
			};
		},
		computed: {
			authorName(){
				return this.username.slice(0,1)
			}
		},
		components: {
			shoppingItems,
			unNavigation,
		}
	}
</script>

<style lang="scss">
	.author {
		@include flex-layout(none, center);
		flex-wrap: wrap;
		padding: 10px;
		padding-top:60px;
		background: #FE2745;
		color: #ffffff;

		.author-picture {
			width: 50px;
			height: 50px;
			line-height: 50px;
			border-radius: 50%;
			// background-color: red;
			border: 2px solid #000;
			text-align: center;
			font-size: 28px;
			
		}

		.user-message {
			width: 80%;
			margin-left: 20rpx;
			font-size: 12px;

			.username {
				width: 100%;
				display: block;
				font-size: 20px;
			}
			text {
				font-size: 14px;
				margin-right: 10px;
			}
		}

		.commodity-status {
			width: 100%;
			margin-top: 20px;
			@include flex-layout(space-between);

			view {
				width: 33%;
				text {
					text-align: center;
					display: block;
					font-size: 16px;
					font-weight: 700;

					&.count {
						margin-bottom: 5px;
					}
				}
			}

		}



	}

	.order-messsage {
		@include flex-layout(center, center);
		height: 100px;
	}

	.discounts {
		@include flex-layout(center, center);
		height: 100px;
		margin-top: 20px;
	}
	.serve {
		@include flex-layout(center, center);
		height: 200px;
		
		.serve-title {
			font-size: 14px;
			font-weight: 700;			
		}
		
		
		text {
			font-size: 16px;
			width: 100%;
			display: block;
			padding-left: 20px;
		}
		
	}
</style>
