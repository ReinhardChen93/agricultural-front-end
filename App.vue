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
		}
	}
</script>

<style lang="scss">
	/*每个页面公共css */
	/* uview-ui公共样式 */
	@import "uview-ui/index.scss";
	/* 引入animate动画库 */
	@import url("./common/animate.css");
	/* 引入free样式库 */
	@import url("./common/free.css");
	/* 引入全局样式库 */
	@import url("./common/common.css");
	/* 引入自定义图标库 */
	@import url("./common/icon.css");
	
</style>
