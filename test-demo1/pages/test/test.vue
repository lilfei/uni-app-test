<template>
	<view class="container">
		<view class="list" v-for="(item,index) in list" :key="'list_'+index" @click="goDetailPage(item.path)">
			<text>{{item.name}}</text>
		</view>
		<view style="height: 10upx"></view>
		<view class="list-media" v-for="(item,index) in mediaList" :key="'dedia_'+index" @click="goDediaDetailPage(item.path)">
			<text>{{item.name}}</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [{
						name: "view_test",
						path: "view_test",
					},
					{
						name: "scroll_view_test",
						path: "scroll_view_test",
					},
					{
						name: "swiper_test",
						path: "swiper_test",
					},
					{
						name: "movable_area_test",
						path: "movable_area_test",
					},
					{
						name: "progress_test",
						path: "progress_test",
					},
					{
						name: "button_test",
						path: "button_test",
					},
					{
						name: "checkbox_test",
						path: "checkbox_test",
					},
					{
						name: "editor_test",
						path: "editor_test",
					},
					{
						name: "form_test",
						path: "form_test",
					},
					{
						name: "input_test",
						path: "input_test",
					},
					{
						name: "label_test",
						path: "label_test",
					},
					{
						name: "navigator_test",
						path: "navigator_test",
					},
				],
				mediaList: [{
						name: "audio_test",
						path: "audio_test",
					},
					{
						name: "camera_test",
						path: "camera_test",
					},
					{
						name: "image_test",
						path: "image_test",
					},
					{
						name: "video_test",
						path: "video_test",
					},
					{
						name: "map_test",
						path: "map_test",
					},
					{
						name: "canvas_test",
						path: "canvas_test",
					},
					{
						name: "webview_test",
						path: "webview_test",
					},
				],
			}
		},
		methods: {
			goDetailPage(url) {
				if (this.navigateFlag) {
					return;
				}

				// HTML5+ 规范
				// #ifdef APP-PLUS || APP-PLUS-NVUE || H5 || MP-ALIPAY || MP-BAIDU || MP-TOUTIAO || MP-QQ
				if (url == "editor_test") {
					uni.showToast({
						title: '只有微信小程序才可用'
					});
					return;
				}
				// #endif

				// 微信小程序
				// #ifdef MP-WEIXIN
				// #endif

				this.navigateFlag = true;
				uni.navigateTo({
					url: '/pages/test_all/' + url + '/' + url
				})
				setTimeout(() => {
					this.navigateFlag = false;
				}, 200)
			},
			goDediaDetailPage(url) {
				if (this.navigateFlag) {
					return;
				}
				
				// HTML5+ 规范
				// #ifdef APP-PLUS || APP-PLUS-NVUE || H5 || MP-ALIPAY || MP-TOUTIAO 
				if (url == "camera_test") {
					uni.showToast({
						title: '只有微信,百度,QQ小程序才可用'
					});
					return;
				}
				// #endif
				
				this.navigateFlag = true;
				uni.navigateTo({
					url: '/pages/media/' + url + '/' + url
				})
				setTimeout(() => {
					this.navigateFlag = false;
				}, 200)
			}
		},

		onLoad(e) {
			console.log("onLoad: ", e)
		},
		onShow(e) {
			console.log("onShow: ", e)
		},
		onReady(e) {
			console.log("onReady: ", e)
		},
		onHide(e) {
			console.log("onHide: ", e)
		},
		onUnload(e) {
			console.log("onUnload: ", e)
		},
		onResize(e) {
			console.log("onResize: ", e)
		},
		onPullDownRefresh(e) {
			console.log("onPullDownRefresh: ", e)
		},
		onReachBottom(e) {
			console.log("onReachBottom: ", e)
		},

		/**
		 * @param {String} index 被点击tabItem的序号，从0开始
		 * @param {String} pagePath 被点击tabItem的页面路径
		 * @param {String} text 被点击tabItem的按钮文字
		 */
		onTabItemTap(index, pagePath, text) {
			console.log("onTabItemTap: ", index)
		},

		onShareAppMessage(e) {
			console.log("onShareAppMessage: ", e)
		},

		/**
		 * @param {Number} scrollTop 页面在垂直方向已滚动的距离（单位px）
		 */
		onPageScroll(scrollTop) {
			console.log("onPageScroll: ", scrollTop)
		},

		/**
		 * @param {Number} index 原生标题栏按钮数组的下标
		 */
		onNavigationBarButtonTap(index) {
			console.log("onNavigationBarButtonTap: ", index)
		},

		/**
		 * @param {String} from	触发返回行为的来源：'backbutton'——左上角导航栏按钮及安卓返回键；'navigateBack'——uni.navigateBack() 方法。
		 */
		onBackPress(from) {
			console.log("onBackPress: ", from)
		},
		onNavigationBarSearchInputChanged(e) {
			console.log("onNavigationBarSearchInputChanged: ", e)
		},
		onNavigationBarSearchInputConfirmed(e) {
			console.log("onNavigationBarSearchInputConfirmed: ", e)
		},
		onNavigationBarSearchInputClicked(e) {
			console.log("onNavigationBarSearchInputClicked: ", e)
		}
	}
</script>

<style>
	.container {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.list {
		display: flex;
		margin-bottom: 2upx;
		background-color: #1AAD19;
		shape-margin: inherit;
		width: 100%;
		align-items: center;
		justify-content: center;
		border: #DD524D;
	}
	
	.list-media {
		display: flex;
		margin-bottom: 2upx;
		background-color: #66AAFF;
		shape-margin: inherit;
		width: 100%;
		align-items: center;
		justify-content: center;
		border: #DD524D;
	}
</style>
