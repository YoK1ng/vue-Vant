<template>
	<div id="app">
		<van-nav-bar class="bar" title="基层农技推广服务平台">
			<van-icon name="search" slot="right" @click="bt()" />
		</van-nav-bar>

		<van-search placeholder="请输入商品名称" v-model="value" v-show="isShow" />

		<van-swipe :autoplay="3000">
			<van-swipe-item v-for="(image, index) in images" :key="index">
				<img :src="image.pic" />
			</van-swipe-item>
		</van-swipe>

		<van-notice-bar mode="closeable">
			足协杯战线连续第2年上演广州德比战，上赛季半决赛上恒大以两回合5-3的总比分淘汰富力。
		</van-notice-bar>

		<van-row>
			<van-col span="6">
				<van-icon name="wap-home" />
				<p>主页</p>
			</van-col>
			<van-col span="6">
				<van-icon name="point-gift" />
				<p>礼物</p>
			</van-col>
			<van-col span="6">
				<van-icon name="free-postage" />
				<p>快递</p>
			</van-col>
			<van-col span="6">
				<van-icon name="cash-back-record" />
				<p>钱包</p>
			</van-col>
		</van-row>

		<van-panel title="热门新闻">
			<van-row v-for="i in news" class="news">
			  	<van-col span="4"><img :src="i.pic"></van-col>
			  	<van-col span="20"><h2>{{i.h1}}</h2><p>{{i.p}}</p></van-col>
			</van-row>
		</van-panel>

		<van-tabbar v-model="active">
			<van-tabbar-item icon="edit">表单</van-tabbar-item>
			<van-tabbar-item icon="pending-orders">列表</van-tabbar-item>
			<van-tabbar-item icon="contact">用户</van-tabbar-item>
			<van-tabbar-item icon="wap-home">登录</van-tabbar-item>
		</van-tabbar>

	</div>
</template>

<script>
	import { Swipe, SwipeItem, NavBar, Icon, Row, Col, NoticeBar, Tabbar, TabbarItem, Search, Panel, List} from 'vant';

	export default {
		components: {
			[Swipe.name]: Swipe,
			[SwipeItem.name]: SwipeItem,
			[NavBar.name]: NavBar,
			[Icon.name]: Icon,
			[Row.name]: Row,
			[Col.name]: Col,
			[NoticeBar.name]: NoticeBar,
			[Tabbar.name]: Tabbar,
			[TabbarItem.name]: TabbarItem,
			[Search.name]: Search,
			[Panel.name]: Panel,
		},
		data() {
			return {
				images: [
					{
						pic: '../static/banner1.jpg',
					},
					{
						pic: '../static/banner2.jpg',
					}
				],
				news:[
					{
						pic: '../static/banner1.jpg',
						h1:'自定义指令 — Vue.js',
						p:'除了核心功能默认内置的指令 (v-model 和v-show),Vue 也允许注册自定义指令。注意,在 Vue2.0 中,代码复用和抽象的主要形式是组件...'
					},
					{
						pic: '../static/banner2.jpg',
						h1:'自定义指令 — Vue.js',
						p:'除了核心功能默认内置的指令 (v-model 和v-show),Vue 也允许注册自定义指令。注意,在 Vue2.0 中,代码复用和抽象的主要形式是组件...'
					},
					{
						pic: '../static/banner1.jpg',
						h1:'自定义指令 — Vue.js',
						p:'除了核心功能默认内置的指令 (v-model 和v-show),Vue 也允许注册自定义指令。注意,在 Vue2.0 中,代码复用和抽象的主要形式是组件...'
					}
				],
				active: 0,
				isShow: false,
				value: '',
				list: [],
				loading: false,
				finished: false
			};
		},
		methods: {
			bt: function() {
				this.isShow = !this.isShow;
			},

		}
	};
</script>

<style>
	body {
		background-color: #f8f8f8;
	}

	.bar {
		background: #448BE3;
		box-shadow: 0 1px 6px #448BE3;
		font-size: 18px;
		color: #fff;
	}

	.bar .van-icon {
		font-size: 14px;
		color: #fff;
	}

	.van-search{
		position: fixed;
		top: 46px;
		left: 0px;
		right: 0px;
		z-index: 99;
	}

	.van-swipe img {
		width: 100%;
	}

	.van-row {
		overflow: hidden;
		background: #fff;
		padding: 20px 0px;
	}

	.van-col-6 {
		text-align: center;
	}

	.van-col-6 .van-icon {
		font-size: 20px;
		width: 40px;
		height: 40px;
		background: #339ae5;
		line-height: 40px;
		border-radius: 35%;
		text-align: center;
		color: #fff;
	}

	.van-col-6:nth-child(1) .van-icon {
		background: #339ae5;
	}

	.van-col-6:nth-child(2) .van-icon {
		background: #f37973;
	}

	.van-col-6:nth-child(3) .van-icon {
		background: #27b7c6;
	}

	.van-col-6:nth-child(4) .van-icon {
		background: #f9a01e;
	}

	.van-col-6 p {
		margin: 5px 0px 0px 0px;
		font-size: 12px;
	}

	.van-panel {
		margin-top: 20px;
	}
	.news{
		padding: 15px;
		height: 60px;
		border-bottom: 1px solid #f2f2f2;
	}
	.news img{
		width: 100%;
		height: 60px;
		border-radius: 2px;
	}
	.news h2{
		margin: 0px 0px 0px 10px;
		font-size: 12px;
		color: #444;
	}
	.news p{
		margin: 5px 0px 0px 10px;
		font-size: 12px;
		color: #999;
	}
</style>