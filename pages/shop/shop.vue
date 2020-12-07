<template>
	<view>
		<u-cell-group>
			<u-cell-item icon="share" title="停车坐爱枫林晚" :arrow="true" arrow-direction="down"></u-cell-item>
			<u-cell-item icon="map" title="霜叶红于二月花" :arrow="false" @tap="openPage('pest')"></u-cell-item>
		</u-cell-group>
		<u-icon name="photo"></u-icon>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {
			openPage(path) {
				uni.navigateTo({
					url: '/pages/'+path+'/'+path,
				});
			}
		}
	}
</script>

<style>

</style>
