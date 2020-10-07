<template>
	<view>
		<image v-if="_props.item.icon" :src="_props.item.icon"></image>
		<text>{{_props.item.count}}</text>
		<text>{{_props.item.text}}</text>
	</view>
</template>

<script>
	export default {
		props: ["item"],
		mounted() {
			// console.log(this._props.item)
		}
	}
</script>

<style lang="scss">
	view {
		width: 25%;
		text-align: center;
		font-size: 14px;

		image {
			width: 35px;
			height: 35px;
		}

		text {
			display: block;
			line-height: 26px;
		}
	}
</style>
