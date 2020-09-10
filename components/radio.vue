<template>
	<view>
		<view class="radio" @click="toggle">
			<icon type="success" size="24" v-show="_props.select" />
		</view>
	</view>
</template>

<script>
	export default {
		props: ["select"],
		data() {
			return {

			};
		},
		methods: {
			toggle() {
				this.$emit("toggle")
			}
		}
	}
</script>

<style lang="scss" scoped>
	.radio {
		width: 24px;
		height: 24px;
		float: left;
		overflow: hidden;
		border-radius: 50%;
		// background: red;
		border: 1px solid #ccc;
		// text-align: center;
		// font-size: 18px;
		// color: #fff;
	}
</style>
