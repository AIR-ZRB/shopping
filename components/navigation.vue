<template>
	<view class="navigation">
		<image src="../static/icon/left-arrow.png"></image>
		<slot></slot>
		<image src="../static/icon/else.png"></image>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss" scoped>
.navigation {
	box-sizing: border-box;
	width: 100%;
	height: 45px;
	border-bottom: 1px solid #eee;
	padding: 0 10px;
	@include flex-layout(space-between,center);
	font-size: 18px;
	image {
		height: 20px;
		width: 20px;
	}
}
</style>
