<template>
	<view class="shopping-car">
		<clearCar v-if="commodity.length === 0" />
		<commodity v-else v-for="item in commodity" :key="item.name + item.storeName" :items.sync="item" :allData="commodity"
		 @editCommodity="editCommodity" ref="test" />
		<!-- 底下结算合计 -->
		<view class="total">
			<view class="all-select">
				<un-radio :select="allSelect" @toggle="allSelectToggle" />
				<text>全选</text>
			</view>
			<view class="total-money">
				<text>{{totalMoney}}</text>
				<button size="mini">{{totalCount}}</button>
			</view>
		</view>
	</view>
</template>

<script>
	import clearCar from "./clearCar.vue";
	import commodity from "./commodity.vue";
	import unRadio from "../../components/radio.vue";
	export default {
		data() {
			return {
				allSelect: false,
				// 假数据
				commodity: [{
						storeName: "青空自营",
						children: [{
							name: "PS4 超强游戏机，各大平台游戏主机",
							picture: "",
							price: "4000",
							select: "标准普通版",
							check: false,
							count: "1",
						}, {
							name: "红米K30至尊版 超强技能手机，性价比之王",
							picture: "",
							price: "2000",
							select: "标准普通版",
							check: false,
							count: "1",
						}]
					},
					{
						storeName: "PDD旗舰店",
						children: [{
							name: "Redmi 9",
							picture: "",
							price: "1000",
							select: "标准普通版",
							check: false,
							count: "1",
						}],
					},
				]
			};
		},
		methods: {
			editCommodity(datas) {
				var editIndex = this.commodity.findIndex((item) => item.storeName === datas.storeName)
				this.$set(this.commodity, editIndex, datas)
			},
			allSelectToggle() {
				this.allSelect = !this.allSelect;
				this.$refs.test.forEach(item => item.$emit("allSelect", this.allSelect))
			},
		},
		computed: {
			totalMoney() {
				let allMoney = 0;
				this.commodity.forEach(item => {
					item.children.forEach(items => {
						if (items.check === true) allMoney += items.price * items.count;
					})
				})
				return `总计: ${allMoney}`;
			},
			totalCount() {
				let count = [];
				this.commodity.forEach(item => {
					// count = item.children.filter(items => items.check == true)
					item.children.filter(items => {
						if (items.check == true) count.push(items)
					})
				})
				return `去结算 ${count.length} 件`;
			}
		},
		components: {
			clearCar,
			commodity,
			unRadio
		}
	}
</script>

<style lang="scss">
	.shopping-car {
		background-color: #fafafa;
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
			@include flex-layout(center, center)
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
</style>
