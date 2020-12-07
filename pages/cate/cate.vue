<template>
	<view>
		<u-action-sheet :list="list" v-model="show"></u-action-sheet>
		<u-cell-group>
			<u-cell-item icon="share" title="停车坐爱枫林晚" :arrow="true" arrow-direction="down"></u-cell-item>
			<u-cell-item icon="map" title="霜叶红于二月花" :arrow="false"></u-cell-item>
		</u-cell-group>
		<u-icon name="photo"></u-icon>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [
					{
					text: '点赞',
					color: 'blue',
					fontSize: 28
					}, {
						text: '分享'
					}, {
						text: '评论'
					}],
				show: true
			}
		},
		methods: {
			
		}
	}
</script>

<style>

</style>
