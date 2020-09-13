<template>
	<view class="clear-car">
		
		<view>
			<image src="https://img11.360buyimg.com/jdphoto/s180x180_jfs/t18163/292/540553659/74408/adeb7463/5a93c51cN3bb5e37b.png"></image>
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
			border-radius: 50%;
			margin-bottom: 10px;
			@include flex-layout(center,center);
			image {
				width: 90px;
				height: 90px;
			}
		}
		
		text {
			width: 100%;
			text-align: center;
			font-size: 16px;
		}
	}
</style>
