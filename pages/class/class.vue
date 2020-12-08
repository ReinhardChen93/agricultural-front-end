<template>
	<view>
		<view>
			<u-tabs-swiper ref="uTabs" :list="list" :current="current" @change="tabsChange" :is-scroll="false"
			 swiperWidth="750"></u-tabs-swiper>
		</view>
		<swiper :current="swiperCurrent" @transition="transition" @animationfinish="animationfinish" style="height: 500px">
			<swiper-item class="swiper-item" v-for="(item, index) in tabs" :key="item.id">
				<scroll-view scroll-y style="height: 100%;width: 100%;" @scrolltolower="onreachBottom">
					<!-- 轮播图组件 -->
					<view>
						<view class="px-3 py-2">
							<swiper-dot :info="swipers" :current="current">
								<swiper :current="current" circular :autoplay="true" :interval="3000" :duration="150" style="height: 250rpx;" @change="changeSwiper">
									<swiper-item v-for="(swiper,swiperIndex) in swipers" :key="swiper.id">
										<image :src="swiper.src" mode="aspectFill"
										style="height: 250rpx;width: 100%;"
										class="rounded-lg"></image>
									</swiper-item>
								</swiper>
							</swiper-dot>
						</view>
						
						<!-- 视频列表 -->
						<card title="为你推荐">
						<view class="f-list">
							
							<media-list v-for="(video,videoIndex) in list3" :key="video.id"
							:item="video" :index="videoIndex"></media-list>
							
						</view>
						</card>
					</view>
				</scroll-view>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
	import swiperDot from '@/components/common/swiper-dot.vue';
	import card from '@/components/common/card.vue';
	import mediaList from '@/components/common/media-list.vue';
	export default {
		components: {
			swiperDot,
			card,
			mediaList
		},
		data() {
			return {
				swipers: [{
					src:"/static/demo/swiper/1.jpg",
					title:"xxx"
				},{
					src:"/static/demo/swiper/2.jpg",
					title:"xxx"
				},{
					src:"/static/demo/swiper/3.jpg",
					title:"xxx"
				}],
				SwiperCurrent: 0, // 轮播index
				list3:[{
					cover:"/static/demo/list2/1.jpg",
					title:"菠萝种植技术",
					author:"李德华",
					Rank: "农科院教授",
					play_count:0,
					danmu_count:0,
					id: Math.random().toString(16)
				}],
				list: [{
					name: '课堂',
					id: Math.random().toString(16)
				}, {
					name: '短视频',
					id: Math.random().toString(16)
				}],
				// 因为内部的滑动机制限制，请将tabs组件和swiper组件的current用不同变量赋值
				current: 0, // tabs组件的current值，表示当前活动的tab选项
				swiperCurrent: 0, // swiper组件的current值，表示当前那个swiper-item是活动的
				tabs: [
					{name: '', id: Math.random().toString(16)},
					{name: '', id: Math.random().toString(16)},
				]
			};
		},
		methods: {
			// tabs通知swiper切换
			tabsChange(index) {
				this.swiperCurrent = index;
			},
			// swiper-item左右移动，通知tabs的滑块跟随移动
			transition(e) {
				let dx = e.detail.dx;
				this.$refs.uTabs.setDx(dx);
			},
			// 由于swiper的内部机制问题，快速切换swiper不会触发dx的连续变化，需要在结束时重置状态
			// swiper滑动结束，分别设置tabs和swiper的状态
			animationfinish(e) {
				let current = e.detail.current;
				this.$refs.uTabs.setFinishCurrent(current);
				this.swiperCurrent = current;
				this.current = current;
			},
			// scroll-view到底部加载更多
			onreachBottom() {
				
			},
			changeSwiper(e){
				this.SwiperCurrent = e.detail.current
			},
		}
	};
</script>
<style>
	.f-list{
		display: flex;
		flex-wrap: wrap;
		padding-left: 15rpx;
		padding-right: 15rpx;
	}
</style>