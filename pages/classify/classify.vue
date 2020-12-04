<template>
	<view>
		<un-navigation>
			<text>分类</text>
		</un-navigation>

		<view class="classify-content">
			<view class="left-menu">
				<view v-for="(item,index) in classify" :key="item.name" :class="['list',item.active === true ? 'active': '']"
				 @click="toggle(index)" :data-active="item.active" v-select>
					{{item.name}}
				</view>
			</view>
			<view class="right-details" v-if="selectNow.length != 0">
				<text class="classify-title">{{selectNow.name}}</text>
				<view class="list" v-for="item in selectNow.children" :key="item.name">
					<image :src="item.image"></image>
					<text>{{item.name}}</text>
				</view>
			</view>
		</view>


	</view>
</template>

<script>
	import unNavigation from "../../components/navigation.vue";
	export default {
		data() {
			return {
				selectNow: [],
				classify: [{
						name: "热门推荐",
						active: true,
						children: [{
								name: "空调",
								image: "//img11.360buyimg.com/focus/s140x140_jfs/t1/117080/5/10502/18158/5ef0103eE416ae569/898a7ac882ba6c63.jpg"
							},
							{
								name: "冰箱",
								image: "//img10.360buyimg.com/focus/s140x140_jfs/t1/119891/13/5448/24096/5ef01048E096cfd33/260803efca5e8a73.jpg"
							},
							{
								name: "电脑",
								image: "//img12.360buyimg.com/focus/s140x140_jfs/t1/131424/31/274/19042/5ecb3bc2E96ef8448/0188085e6fd6cd12.png"
							},
							{
								name: "手机",
								image: "//img14.360buyimg.com/focus/s140x140_jfs/t27136/183/1628977274/31007/a6f7ed55/5be6ebd8Nb07ef492.png"
							},
							{
								name: "全面屏手机",
								image: "//img20.360buyimg.com/focus/s140x140_jfs/t1/86638/37/11918/19572/5e3e4307E7606f742/0210ac72c0d9275e.jpg"
							},
							{
								name: "游戏手机",
								image: "//img20.360buyimg.com/focus/s140x140_jfs/t1/102972/19/11837/14987/5e3d8bdaEc8ffe21e/6119d3f773fcdacd.jpg"
							},
						]
					}, {
						name: "手机数码",
						active: false,
						children: [{
							name: "小米",
							image: "//img30.360buyimg.com/focus/s140x140_jfs/t13411/188/926813276/3945/a4f47292/5a1692eeN105a64b4.png"
						}, {
							name: "华为",
							image: "//img14.360buyimg.com/focus/s140x140_jfs/t11929/135/2372293765/1396/e103ec31/5a1692e2Nbea6e136.jpg"
						}, {
							name: "荣耀",
							image: "//img10.360buyimg.com/focus/s140x140_jfs/t12178/348/911080073/4732/db0ad9c7/5a1692e2N6df7c609.jpg"
						}, {
							name: "iPhone",
							image: "//img20.360buyimg.com/focus/s140x140_jfs/t13759/194/897734755/2493/1305d4c4/5a1692ebN8ae73077.jpg"
						}, {
							name: "vivo",
							image: "//img11.360buyimg.com/focus/s140x140_jfs/t11014/359/2341377211/2777/1755c29c/5a169244Nff0179e0.png"
						}, {
							name: "OPPO",
							image: "//img13.360buyimg.com/focus/s140x140_jfs/t13036/273/932026474/2570/a3517c7d/5a169254N4bbbd9fb.png"
						}, ]
					},
					{
						name: "电脑办公",
						active: false,
						children: []
					}, {
						name: "家用电器",
						active: false,
						children: []
					}, {
						name: "美妆护肤",
						active: false,
						children: []
					}, {
						name: "个护清洁",
						active: false,
						children: []
					}, {
						name: "汽车生活",
						active: false,
						children: []
					}, {
						name: "男装",
						active: false,
						children: []
					}, {
						name: "男鞋",
						active: false,
						children: []
					}, {
						name: "女装",
						active: false,
						children: []
					}, {
						name: "女鞋",
						active: false,
						children: []
					}, {
						name: "图书音像",
						active: false,
						children: []
					}, {
						name: "户外运动",
						active: false,
						children: []
					},
					{
						name: "内衣配饰",
						active: false,
						children: []
					},
					{
						name: "食品生鲜",
						active: false,
						children: []
					},
					{
						name: "酒水饮料",
						active: false,
						children: []
					},
					{
						name: "家居家装",
						active: false,
						children: []
					},
					{
						name: "家具厨具",
						active: false,
						children: []
					},
				]
			}
		},
		components: {
			unNavigation
		},
		methods: {
			toggle(index) {
				this.classify.forEach((item) => item.active = false);
				this.classify[index].active = true;
				this.selectNow = this.classify[index];
				this.$forceUpdate();
			},
		},
		directives: {
			select: {
				// 指令的定义
				bind(el) {
					if (el.dataset.active) el.click();
				}
			}
		}
	}
</script>

<style lang="scss">
	.classify-content {
		position: relative;
		padding-top: 50px;
		
	}

	.left-menu {
		width: 85px;
		height: 100%;

		.list {
			height: 46px;
			line-height: 46px;
			text-align: center;
			font-size: 14px;
			background: #F8F8F8;
		}

		view.active {
			background: #ffffff;
			color: $theme-color;
		}
	}

	.right-details {
		position: absolute;
		top: 50px;
		padding-left: 85px;
		width: 80%;

		.classify-title {
			display: block;
			width: 100%;
			padding: 10px;
			font-weight: 700;
			font-size: 14px;
		}

		.list {
			width: 33.3%;
			float: left;
			text-align: center;

			image {
				width: 70px;
				height: 70px;
			}

			text {
				display: block;
				height: 35px;
				width: 100%;
				font-size: 14px;
			}
		}
	}
</style>
