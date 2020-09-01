<template>
	<view>
		<text v-if="_props.item.icon">
			{{_props.item.icon}}
		</text>
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

		text {
			display: block;
			line-height: 26px;
		}
	}
</style>
