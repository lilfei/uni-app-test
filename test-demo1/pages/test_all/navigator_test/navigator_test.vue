<template>
	<view>
		<view class="page-body">
			<view class="btn-area">
				<navigator url="../navigate/navigator_test1/navigator_test1?title=navigate" hover-class="navigator-hover">
					<button type="default">跳转到新页面</button>
				</navigator>
				<navigator url="../navigate/redirect_test1/redirect_test1?title=redirect" open-type="redirect" hover-class="other-navigator-hover">
					<button type="default">在当前页打开</button>
				</navigator>
				<navigator url="/pages/mine/mine" open-type="switchTab" hover-class="other-navigator-hover">
					<button type="default">跳转tab页面</button>
				</navigator>
			</view>
		</view>
	</view>
</template>

<script>

</script>

<style>

</style>
