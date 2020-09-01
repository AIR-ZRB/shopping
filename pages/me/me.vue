<template>
	<view class="my">
		<view class="author">
			<view class="author-picture"></view>

			<view class="user-message">
				<text class="username">青空</text>
				<text>青享值：111</text>
				<text>小白信用：111</text>
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
			<text>工具与服务</text>
			<shoppingItems v-for="item in serve" :key="item.text" :item="item" />
		</view>


	</view>
</template>

<script>
	import shoppingItems from "./shopping-items.vue";
	export default {
		data() {
			return {
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
						icon: "icon",
						text: "待付款"
					},
					{
						icon: "icon",
						text: "待收货"
					},
					{
						icon: "icon",
						text: "退换/售后"
					},
					{
						icon: "icon",
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
						icon: "icon",
						text: "客户服务"
					},
					{
						icon: "icon",
						text: "我的预约"
					}, {
						icon: "icon",
						text: "高价回收"
					}, {
						icon: "icon",
						text: "青火车票"
					}, {
						icon: "icon",
						text: "应用推荐"
					}, {
						icon: "icon",
						text: "青机票"
					}, {
						icon: "icon",
						text: "青酒店"
					}, {
						icon: "icon",
						text: "闲置换钱"
					},
				]
			};
		},
		components: {
			shoppingItems
		}
	}
</script>

<style lang="scss">
	.author {
		@include flex-layout(none, center);
		flex-wrap: wrap;
		padding: 10px;
		background: #FE2745;
		color: #ffffff;

		.author-picture {
			width: 60px;
			height: 60px;
			border-radius: 50%;
			background-color: skyblue;
		}

		.user-message {
			width: 80%;
			margin-left: 20rpx;
			font-size: 14px;

			.username {
				width: 100%;
				display: block;
				font-size: 20px;

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
		background: #eee;
	}

	.discounts {
		@include flex-layout(center, center);
		background: #eee;
		height: 100px;
		margin-top: 20px;
	}
	.serve {
		@include flex-layout(center, center);
		
		height: 200px;
		text {
			font-size: 16px;
			width: 100%;
			display: block;
			padding-left: 20px;
		}
		
	}
</style>
