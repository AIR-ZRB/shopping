<template>
	<view class="shopping-car">
		<unNavigation>
			<text>购物车</text>
		</unNavigation>
		<!-- 当购物车为空的时候显示 -->
		<clearCar v-if="commodity.length === 0" />
		<!-- 商品渲染 -->
		<commodity v-else v-for="item in commodity" :key="item.name + item.storeName" :items.sync="item" :allData="commodity"
		 @editCommodity="editCommodity" ref="test" />

		<recommendCommodity />
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
	import unNavigation from "../../components/navigation.vue";
	import recommendCommodity from "../../components/recommendCommodity.vue"
	export default {
		data() {
			return {
				allSelect: false,
				// 假数据
				commodity: [
					{
						storeName: "青空自营",
						children: [{
							name: "PS4 超强游戏机，各大平台游戏主机",
							picture: "//img12.360buyimg.com/n2/s270x270_jfs/t1/150608/14/10886/86065/5fd9c380Eefeabd1f/0255698f4340b68b.jpg!q70.dpg",
							price: "4000",
							select: "标准普通版",
							check: false,
							count: "1",
						}, {
							name: "红米K30至尊版 超强技能手机，性价比之王",
							picture: "//img13.360buyimg.com/n2/s240x240_jfs/t1/138518/8/5212/47697/5f324197Efdfecb90/9a05747b8c2cad02.jpg!q70.jpg",
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
							picture: "//img14.360buyimg.com/n2/s240x240_jfs/t1/146723/14/1327/184448/5ef09479E3e33a015/38a379a4543151d1.jpg!q70.jpg",
							price: "1000",
							select: "标准普通版",
							check: false,
							count: "1",
						}, {
							name: "小米手表Color",
							picture: "//img12.360buyimg.com/n2/s240x240_jfs/t1/154865/8/2873/61597/5f8eb677Ef7b54fe4/28e9dfc3ff6b17c4.jpg!q70.jpg",
							price: "799",
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
				this.$set(this.commodity, editIndex, datas);
			},
			allSelectToggle() {
				this.allSelect = !this.allSelect;
				this.$refs.test.forEach(item => item.$emit("allSelect", this.allSelect));
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
			unRadio,
			unNavigation,
			recommendCommodity
		}
	}
</script>

<style lang="scss">
	.shopping-car {
		background-color: #fafafa;
		padding: 50px 0 50px 0;
		// overflow: hidden;
		position: relative;
	}

	.total {
		width: 100%;
		height: 50px;
		background: rgba(255, 255, 255, .8);
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
