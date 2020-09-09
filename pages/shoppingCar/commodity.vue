<template>
	<view class="commodity">
		<!-- 商品名字 -->
		<view class="store-name">
			<radio-group @change="radioChange">
				<un-radio />
				<label class="radio">
					<radio :value="_props.items.storeName" :checked="storeSelect" />
					<text class="name">{{_props.items.storeName}}</text>
				</label>
			</radio-group>
		</view>


		<view class="detail-message" v-for="(items,index) in _props.items.children" :key="items.name+ items.price">
			<!-- 商品图片 -->
			<label class="radio">
				<radio value="" :checked="items.check" />
				<view class="image"></view>
			</label>

			<!-- 商品信息 -->
			<view class="commodity-description">
				<text class="name">{{items.name}}</text>
				<text class="select">{{items.select}}</text>

				<view class="price-count">
					<text class="price">￥{{items.price}}</text>
					<view class="count">
						<text @click="countEdit('subtract',index)">-</text>
						<text>{{items.count}}</text>
						<text @click="countEdit('add',index)">+</text>
					</view>
				</view>

				<view class="commodity-ctrl">
					<text>移除关注</text>
					<text>|</text>
					<text>删除</text>
				</view>
			</view>

		</view>

		<view class="total">
			<view class="all-select">
				<radio :checked="false" />
				<text>全选</text>
			</view>
			<view class="total-money">
				<text>总计：999</text>
				<button size="mini">去结算(?)件</button>
			</view>

		</view>

	</view>
</template>

<script>
	import unRadio from "../../components/radio.vue";
	export default {
		props: ["items"],
		data() {
			return {
				storeSelect: false,
				datas: {}
			}
		},
		components: {
			unRadio
		},
		methods: {
			radioChange(value) {

				this.storeSelect = !this.storeSelect;
				console.log(this.storeSelect);


				this.datas.children.forEach((item) => item.check = this.storeSelect)
				this.$emit("editCommodity", this.datas)

			},
			countEdit(flag, index) {

				if (flag === "add") this.datas.children[index].count = parseInt(this.datas.children[index].count) + 1;

				if (flag === "subtract") {
					if (this.datas.children[index].count <= 1) return;
					this.datas.children[index].count = parseInt(this.datas.children[index].count) - 1;
				}
				this.$emit("editCommodity", this.datas)
			}
		},
		created() {
			this.datas = JSON.parse(JSON.stringify(this._props.items));

		}


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
			@include flex-layout(flex-start);
			padding-bottom: 20px;

			.radio {
				@include flex-layout(center, center);
				float: left;
				position: absolute;


				.image {
					width: 135rpx;
					height: 135rpx;
					background-color: red;
					margin: 0 0 0 10px;
				}
			}



			// 商品详细信息
			.commodity-description {
				box-sizing: border-box;
				overflow: hidden;
				margin-left: 220rpx;

				width: 100%;
				position: relative;



				.name {
					display: block;
					// font-size: 18px;
					font-size: 30rpx;
				}

				.select {
					// font-size: 14px;
					display: inline-block;
					font-size: 28rpx;
					$select-height: 24px;
					height: $select-height;
					border-radius: $select-height / 2;
					background-color: #F2F2F2;
					padding: 0 4px;
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

		.total {
			width: 100%;
			height: 50px;
			background: rgba(255, 255, 255, .8);
			// background: red;
			position: fixed;
			bottom: 50px;
			left: 0;
			font-size: 18px;
			@include flex-layout(space-between, center);

			.all-select {
				font-size: 14px;
				margin-left: 10px;
			}

			.total-money {
				@include flex-layout(space-between, center);
				font-size: 18px;
				margin-right: 10px;

				text {
					font-weight: 700;
					margin-right: 10px;
				}

				button {
					background: $theme-color;
					color: white;
					border-radius: 30px
				}
			}
		}
	}
</style>
