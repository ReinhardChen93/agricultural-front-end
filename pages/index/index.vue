<template>
	<view>
		
	</view>
</template>

<script>
	
	export default {
		components: {
			
		},
		data() {
			return {
				current:0,
				swipers: [{
					src:"/static/demo/swiper/1.jpg",
					title:"xxx"
				},{
					src:"/static/demo/swiper/2.jpg",
					title:"xxx"
				},{
					src:"/static/demo/swiper/3.jpg",
					title:"xxx"
				}]
			}
		},
		onLoad() {

		},
		onNavigationBarSearchInputClicked() {
			console.log('点击了搜索框');
		},
		onNavigationBarButtonTap(e) {
			console.log("点击了按钮");
		},
		methods: {
			changeSwiper(e){
				this.current = e.detail.current
			}
		}
	}
</script>

<style>

</style>
