<template>
	<view class="message" v-if="_props.show">
		{{_props.text}}
	</view>
</template>

<script>
	export default {
		props: {
			duration: {
				default: 2000,
				type: Number
			},
			text: {
				default: "这是一条提示消息",
				type: String
			},
			type: {
				default: "success",
				type: String
			},
			show: {
				default: false,
				type: Boolean
			}
		},
		data() {
			return {

			};
		}
	}
</script>

<style lang="scss" scoped>
	.message {
		width: 50%;
		padding: 5px 0;
		position: fixed;
		top: 40px;
		left: 50%;
		transform: translateX(-50%);
		text-align: center;
		background: #F0F9EB;
		color: #67C23A;
		font-size: 14px;
		border-radius: 5px // left: 0;
	}

	// uni不支持transition
	.fade-enter,
	.fade-levea-to {
		transfrom: translateY(-200px);
	}

	.fade-enter-to,
	.fade-leave {
		transfrom: translateY(0px);
	}

	.fade-enter-active,
	.fade-leave-active {
		transition: all .3s;
	}
</style>
