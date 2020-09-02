<template>
	<view class="shopping-car">
		<clearCar v-if="commodity.length === 0" />
		<commodity v-else
			v-for="item in commodity"
			:key="item.name + item.storeName"
			:items= "item"
		/>
		
	</view>
</template>

<script>
	import clearCar from "./clearCar.vue";
	import commodity from "./commodity.vue";
	export default {
		data() {
			return {
				// 假数据
				commodity: [
					{
						name: "PS4",
						picture: "",
						price: "4000",
						select: "标准普通版",
						check: false,
						count: "1",
						storeName: "青空自营",
					},
					{
						name: "红米K30至尊版",
						picture: "",
						price: "2000",
						select: "标准普通版",
						check: false,
						count: "1",
						storeName: "青空自营",
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
