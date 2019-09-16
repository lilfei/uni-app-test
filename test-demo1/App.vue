<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		},
		onUniNViewMessage: function(e) {
			console.log("onUniNViewMessage:" + e)
		}
	}
</script>

<style>
	/*每个页面公共css */
	@import './common/uni.css';
	@import './common/llf.css';
</style>
