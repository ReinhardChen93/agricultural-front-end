<template>
	<view style="width: 100%;" class="flex align-center py-2 border-bottom">
		<image :src="item.cover" style="width: 260rpx;height: 160rpx;" class="rounded-lg mx-2 flex-shrink"></image>
		<view class="flex-1 flex flex-column desc" style="height: 160rpx;">
			<text class="font title" style="line-height: 1.2;">{{item.title}}</text>
			<view class="flex">
				<text class="font-sm mt-auto">{{item.author}}</text>
				<text class="font-sm text-light-muted mt-auto" style="margin-left: 10rpx;">{{item.Rank}}</text>
			</view>
			<view class="flex align-center justify-between text-muted line-h">
				<view class="line-h">
					<text class="iconfont iconbofangshu font-md mx-1"></text>
					<text class="font-sm">{{item.play_count}}</text>
				</view>
				<view class="line-h">
					<text class="iconfont icondanmushu font-md mx-1"></text>
					<text class="font-sm">{{item.danmu_count}}</text>
				</view>
				<text class="iconfont icongengduo"></text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		props: {
			item: Object,
			index:[String,Number]
		},
	}
</script>

<style>
	.title {
		display: -webkit-box;
		-webkit-box-orient: vertical;
		-webkit-line-clamp: 2;
		overflow: hidden;
	}
	.desc {
		justify-content: space-between;
	}
</style>
