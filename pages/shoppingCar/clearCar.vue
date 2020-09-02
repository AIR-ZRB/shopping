<template>
	<view class="clear-car">
		
		<view>
			这是一张图
		</view>
		
		<text>
			购物车空空如也，去逛逛吧~
		</text>

	</view>
</template>

<script>
</script>

<style lang="scss">
	.clear-car {
		@include flex-layout(center,center);
		view {
			width: 140px;
			height: 140px;
			border-radius: 50%;
			background: red;
			margin-bottom: 10px;
			@include flex-layout(center,center);
		}
		
		text {
			width: 100%;
			text-align: center;
			font-size: 16px;
		}
	}
</style>
