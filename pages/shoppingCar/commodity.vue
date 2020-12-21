<template>
	<view class="commodity">
		<!-- 商品名字 -->
		<view class="store-name">
			<un-radio :select="storeSelect" @toggle="radioChange" />
			<text class="name">{{_props.items.storeName}}</text>
		</view>


		<view class="detail-message" v-for="(items,index) in _props.items.children" :key="items.name+ items.price">
			<!-- 商品图片 -->
			<view class="radio">
				<un-radio :select="items.check" @toggle="itemsChange(index)" />
				<!-- <view class="image"></view> -->
				<image class="image" :src="items.picture"></image>
			</view>



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
	</view>
</template>

<script>
	import unRadio from "../../components/radio.vue";
	export default {
		props: ["items"],
		data() {
			return {
				storeSelect: false,
				datas: {},
			}
		},
		components: {
			unRadio
		},
		// 商品没选中，店铺会继续选中
		methods: {
			radioChange(value = !this.storeSelect) {
				// 店铺全选
				this.storeSelect = value;
				this.datas.children.forEach((item) => item.check = value)
				this.$emit("editCommodity", this.datas)
			},
			itemsChange(index) {
				// 单个商品选中
				this.datas.children[index].check = !this.datas.children[index].check;
				const flag = this.datas.children.every(item => item.check === true);
				const flags = this.datas.children.some(item => item.check === false);


				flag && this.radioChange();
				if (flags === true) {
					if (this.storeSelect === true) this.storeSelect = false;
				}

				this.$emit("editCommodity", this.datas)
			},
			countEdit(flag, index) {

				if (flag === "add") this.datas.children[index].count = parseInt(this.datas.children[index].count) + 1;

				if (flag === "subtract") {
					if (this.datas.children[index].count <= 1) return;
					this.datas.children[index].count = parseInt(this.datas.children[index].count) - 1;
				}
				this.$emit("editCommodity", this.datas)
			},

		},
		created() {
			this.datas = JSON.parse(JSON.stringify(this._props.items));
			this.$on("allSelect", (value) => this.radioChange(value))
		}


	}
</script>

<style lang="scss">
	.commodity {
		// margin-top: ;
		padding: 20px 10px;
		background: white;
		border-radius: 5px;
		margin-bottom: 20px;

		.store-name {
			@include font-size(28rpx, 18px);
			font-weight: 700;
			margin-bottom: 20px;
		}

		.detail-message {
			@include flex-layout(flex-start);
			padding-bottom: 50px;

			.radio {
				@include flex-layout(center, center);
				float: left;
				position: absolute;

				.image {
					// background-color: red;
					@include box-size(200rpx, 200rpx, 144px, 144px);
					border-radius: 5px;
				}
			}

			// 商品详细信息
			.commodity-description {
				box-sizing: border-box;
				overflow: hidden;

				width: 100%;
				position: relative;
				@include margin-left-size(300rpx, 210px);

				.name {
					display: block;
					padding: 5px 0 0 0;
					@include font-size(22rpx, 18px);
				}

				.select {
					display: inline-block;
					@include font-size(24rpx, 14px);
					border-radius: 10px;
					background-color: #F2F2F2;
					padding: 1px 10px;
					margin: 10px 0;
				}

				.price-count {
					@include flex-layout(space-between, center);

					.price {
						@include font-size(32rpx, 20px);
						font-weight: 700;
						color: $theme-color;
					}

					.count {
						@include flex-layout(center, center);

						text {
							display: block;


							&:first-child,
							&:last-child {

								@include font-size(32rpx, 14px);
								font-weight: 700;
							}

							&:nth-child(2) {

								@include font-size(32rpx, 14px);
								font-weight: 700;
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
					@include flex-layout(flex-end);

					text {
						font-size: 12px;
						margin-left: 5px;
					}
				}
			}
		}


	}
</style>
