<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
		<view class="count-area">
			<button class="button-style" v-on:click="add()">add</button>
			<text class="count">{{count}}</text>
			<button class="button-style" v-on:click="minus()">minus</button>
		</view>
		<button class="toast-test" v-on:click="show()">toastTest</button>
		<view class="list" v-for="(item,index) in listArray" :key="index">
			<view class="list-item">
				<text>{{item}}</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				count: 0,
				listArray: ['数据1', '数据2', '数据3']
			}
		},
		onLoad() {

		},
		methods: {
			add: function() {
				this.count++
			},
			minus: function() {
				this.count--
			},
			show: function() {
				uni.showToast({
					title: 'toastTest',
					mask: false,
					duration: 1500,
				})
			}
		},
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		height: 100%;
	}

	.logo {
		height: 100upx;
		width: 100upx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 20upx;
		color: #8f8f94;
	}

	.count-area {
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-content: center;
	}

	.count {
		background-color: #4CD964;
		text-align: center;
		color: #DD524D;
		width: 200upx;
		margin-left: 20upx;
		margin-right: 20upx;
	}

	.button-style {
		text-align: center;
		text-justify: inherit;
	}

	.toast-test {
		margin: 10upx;
	}

	.list {
		margin: 1upx;
		display: flex;
		width: 100%;
		align-content: center;
		justify-content: center;
	}

	.list-item {
		display: flex;
		background-color: #007AFF;
		width: 100%;
		justify-content: center;
	}
</style>
