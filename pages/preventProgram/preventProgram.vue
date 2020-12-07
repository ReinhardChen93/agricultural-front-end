<template>
	<view class="container">
		<view class="title">
			需要防治的病虫害:<text class="sub-title">根腐病</text>
		</view>
		<view class="imgArea">
			<u-image src="https://cdn.uviewui.com/uview/example/fade.jpg" 
						:lazy-load="true"
						height="10.75rem"
						
						mode="scaleToFill"
			>
				<u-loading slot="loading"></u-loading>
				<view slot="error" style="font-size: 24rpx;">加载失败</view>
			</u-image>
		</view>
		<!-- 症状 -->
		<view class="symptom">
			<view class="symptom-title">
				症状
			</view>
			<text class="symptom-desc">
				初期在绿色果实上可见原型深褐色小斑点，后扩大，中央凹陷，呈灰白色，外部仍为深褐色，而周边缘紫褐色似“鸟眼”状。果实发病后期多个病斑可连接成大斑，随后病斑硬化或龟裂。病果小而酸，发病严重的直接干枯或者枯死。
			</text>
		</view>
		<!-- 预防方案 -->
		<view class="prevent">
			<view class="prevent-title">
				预防方案
			</view>
			<view class="plan">
				<view class="plan-item">
					<view class="product">
						<view class="product-item">
							<u-image class="img" src="https://cdn.uviewui.com/uview/example/fade.jpg"
										:lazy-load="true"
										width="3.63rem"
										height="3.75rem"	
										mode="scaleToFill">
								<u-loading slot="loading"></u-loading>
								<view slot="error" style="font-size: 24rpx;">加载失败</view>
							</u-image>
							<text>腈苯唑(应得)</text>
						</view>
						<u-icon name="plus" color="#101010" size="1rem"></u-icon>
						<view class="product-item">
							<u-image class="img" src="https://cdn.uviewui.com/uview/example/fade.jpg"
										:lazy-load="true"
										width="3.63rem"
										height="3.75rem"	
										mode="scaleToFill">
								<u-loading slot="loading"></u-loading>
								<view slot="error" style="font-size: 24rpx;">加载失败</view>
							</u-image>
							<text>腈苯唑(应得)</text>
						</view>
						<u-icon name="plus" color="#101010" size="1rem"></u-icon>
						<view class="product-item">
							<u-image class="img" src="https://cdn.uviewui.com/uview/example/fade.jpg"
										:lazy-load="true"
										width="3.63rem"
										height="3.75rem"	
										mode="scaleToFill">
								<u-loading slot="loading"></u-loading>
								<view slot="error" style="font-size: 24rpx;">加载失败</view>
							</u-image>
							<text>腈苯唑(应得)</text>
						</view>
					</view>
					<view class="buy-btn">
						<u-button type="primary" size="mini" shape="square" :ripple="true">立即购买</u-button>
					</view>
					
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
	.container {
		display: flex;
		flex-direction: column;
		
		.title {
			display: flex;
			color: rgba(16, 16, 16, 100);
			font-size: 1rem;
			font-weight: bold;
			margin-bottom: 1rem;
			.sub-title {
				margin-left: 1rem;
				font-weight: normal;
			}
		}
		.imgArea {
			flex: 1;
			display: flex;
			justify-content: center;
			height: 10.75rem;
		}
		.symptom {
			display: flex;
			flex-direction: column;
			font-size: 1rem;
			color: rgba(16, 16, 16, 100);
			padding: 0.5rem 0;
			.symptom-title {
				font-weight: normal;
				padding: 0.25rem 0;	
			}
			.symptom-desc {
				font-size: 0.88rem;
			}
		}
		.prevent {
			display: flex;
			flex-direction: column;
			font-size: 1rem;
			color: rgba(16, 16, 16, 100);
			padding: 0.5rem 0;
			.prevent-title {
				font-weight: bold;
				padding: 0.25rem 0;
			}
			.plan {
				width: 100%;
				.plan-item {
					box-sizing: border-box;
					width: 100%;
					height: 6.25rem;
					display: flex;
					justify-content: space-between;
					align-items: center;
					.product {
						box-sizing: border-box;
						flex: 1;
						flex-shrink: 0;
						overflow-x: scroll;
						display: flex;
						// justify-content: space-around;
						align-items: center;
						.product-item{
							display: flex;
							flex-direction: column;
							align-items: center;
							.img {
								width: 3.63rem;
								height: 3.75rem;
								margin: 0.5rem 2rem;
							}
							text {
								font-size:  0.88rem;
							}
						}
						
					}
					.buy-btn {
						width: 5rem;
						margin: 0 1rem;
					}
					
					
				}
			}
		}
	}
</style>
