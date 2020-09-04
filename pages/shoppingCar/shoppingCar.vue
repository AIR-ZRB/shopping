<template>
	<view class="shopping-car">
		<clearCar v-if="commodity.length === 0" />
		<commodity v-else v-for="item in commodity" :key="item.name + item.storeName" :items.sync="item" />

	</view>
</template>

<script>
	import clearCar from "./clearCar.vue";
	import commodity from "./commodity.vue";
	export default {
		data() {
			return {
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
		components: {
			clearCar,
			commodity
		}
	}
</script>

<style lang="scss">
	.shopping-car {
		background-color: #fafafa;
	}
</style>
