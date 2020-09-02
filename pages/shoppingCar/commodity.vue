<template>
	<view class="commodity">
		<view class="store-name">
			<label class="radio">
				<radio value="r1" checked="true" />
				<text class="name">{{_props.items.storeName}}</text>
			</label>


		</view>

		<view class="detail-message">
			<label class="radio">
				<radio value="" checked="true" />
			</label>

			<view class="image"></view>

			<view class="commodity-description">
				<text class="name">{{_props.items.name}}</text>
				<text class="select">{{_props.items.select}}</text>

				<view class="price-count">
					<text class="price">￥{{_props.items.price}}</text>
					<view class="count">
						<text>-</text>
						<text>{{_props.items.count}}</text>
						<text>+</text>
					</view>
				</view>

				<view class="commodity-ctrl">
					<text>移除关注</text>
					<text>|</text>
					<text>删除</text>
				</view>
			</view>


		</view>


	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		props: ["items"]
	}
</script>

<style lang="scss">
	.commodity {
		padding: 20px;
		background: white;
		border-radius: 5px;
		margin-bottom: 20px;

		.store-name {
			font-size: 20px;
			font-weight: 700;
			margin-bottom: 20px;
		}

		.detail-message {
			position: relative;
			@include flex-layout(flex-start,center);

			.image {
				width: 135px;
				height: 135px;
				background-color: red;
				margin:0 0 0 10px;
			}

			.commodity-description {
				box-sizing: border-box;
				width: 100%;
				position: absolute;
				top: 0;
				padding-left: 190px;

				.name {
					display: block;
					// font-size: 18px;
					font-size: 32rpx;
				}

				.select {
					// font-size: 14px;
					font-size: 28rpx;
					$select-height: 24px;
					height: $select-height;
					border-radius: $select-height / 2;
					background-color: #F2F2F2;
					padding: 0 2px;
					margin: 10px 0;
				}

				.price-count {
					@include flex-layout(space-between, center);

					.price {
						// font-size: 18px;
						font-size: 32rpx;
						font-weight: 700;
						color: $theme-color;
					}

					.count {
						@include flex-layout(center, center);

						text {
							display: block;
							// width: 20px;

							&:first-child,
							&:last-child {
								// font-size: 24px;
								font-size: 32rpx;
								font-weight: 700;
								// text-
							}

							&:nth-child(2) {
								// // text-align: center;
								// @include flex-layout(center, center);
								font-size: 32rpx;
								// height: 100%;
								padding: 0 10px;
								margin: 0 5px;
								background: #f2f2f2;
								text-align: center;
							}

						}
					}
				}

				.commodity-ctrl {
					font-size: 12px;
					margin-top: 10px;

					@include flex-layout(flex-end) text {
						margin-left: 5px;
					}
				}
			}
		}

	}
</style>
