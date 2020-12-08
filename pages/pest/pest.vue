<template>
	<view class="pest-container">
		<view class="tool-bar">
			<view class="bar-item"
				  v-for="(item,index) in barText"
				  :key="index"
				  :class="activeIndex === index ? 'item-active' : ''"
				  @tap="changeCate(index)"
				  >
				{{item.name}}
			</view>
		</view>
		<view class="content">
			<view class="classify">
				<view class="title">
					病害 <text class="sub-title">(可多选)</text>
				</view>
				<view class="item" v-for="(item, index) in contentList" :key="item.id">
					<text>{{item.name}}</text>
					<u-checkbox
						@change="(e) => checkboxChange(e, index)"
						v-model="item.checked"
						shape="circle"
						:name="item.name"></u-checkbox>
				</view>
			</view>
		</view>
		<view class="footer-bat">
			<u-button type="primary" :ripple="true" shape="circle" 
			class="footer-btn"
			@click="hundelBtnClick"
			>主要按钮</u-button>
		</view>
		
		<u-toast ref="uToast" />
	</view>
</template>

<script>
	export default {
		data() {
			return {
				activeIndex: 0,
				barText: [
					{name: '病害'},
					{name: '虫害'},
					{name: '生理性病害'},
					{name: '其它'},
				],
				contentList: [
					{id: Math.random().toString(16), name: '根腐病', checked: false},
					{id: Math.random().toString(16), name: '房枯病', checked: false},
					{id: Math.random().toString(16), name: '溃疡病', checked: false},
				]
			};
		},
		methods:{
			changeCate(index) {
				this.activeIndex = index
			},
			/**
			 * @name 记录选择的病害
			 * @param {Object} e
			 * @param {Object} index
			 */
			checkboxChange(e, index) {
				this.contentList[index].checked = e.value
				console.log(this.contentList)
			},
			
			hundelBtnClick(){
				let data = this.contentList.filter(item => item.checked === true)
				console.log(data)
				if(Object.keys(data).length > 0) {
					this.openPage('preventProgram')
				} else {
					this.showToast("warning", "请选择对应病虫害")
				}
				
			},
			
			showToast(type, title, url) {
				this.$refs.uToast.show({
					title: title,
					type: type || 'success',
					url: '/pages/'+url+'/'+url,
				})
			},
			
			openPage(path) {
				uni.navigateTo({
					animationType: 'pop-in',
					animationDuration: 200,
					url: '/pages/'+path+'/'+path,
				});
			}
		}
	}
</script>

<style lang="scss">
	.pest-container {
		display: flex;
		justify-content: space-between;
		height: 100%;
		background-color: rgba(248, 250, 255, 100);
		.tool-bar {
			height: 100%;
			width: 2.5rem;
			margin-right: 1.25rem;
			display: flex;
			flex-direction: column;
			.bar-item {
				flex-shrink: 0;
				padding: 2.5rem 0.625rem;
				line-height: 1.25rem;
				border-radius: 0px 0.38rem 0.5rem 0rem;
				background-color: rgba(255, 255, 255, 100);
				color: rgba(68, 68, 68, 100);
				font-size: 0.88rem;
			}
			.item-active{
				color: rgba(255, 255, 255, 100);
				background-color: rgba(97, 130, 250, 100);
			}
		}
		.content {
			flex: 1;
			height: 100%;
			box-sizing: border-box;
			margin-right: 0.625rem;
			.classify {
				.title {
					display: flex;
					align-items: center;
					color: rgba(16, 16, 16, 100);
					font-size: 1rem;
					
					.sub-title {
						color: rgba(102, 102, 102, 100);
						font-size: 0.88rem;
						margin-left: 0.375rem;
					}
				}
				.item {
					display: flex;
					justify-content: space-between;
					align-items:center;
					width: 100%;
					height: 3rem;
					border-bottom: 1px solid #E5E7F0;
				}
			}
		}
		.footer-bat {
			position: fixed;
			bottom: 2rem;
			left: 0;
			right: 0;
			.footer-btn {
				width: 11rem;
			}
		}
	}

</style>
