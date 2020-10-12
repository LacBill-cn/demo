
<template>
	<view class="navbar">
	<view class="navbar-fixed">
		<!-- 状态栏 -->
		<view class="" :style="{height: statusBarHeight +'px'}">
			<!-- 导航栏 -->
		</view>
		<view class="navbar-content" :style="{height:navBarHeight+'px',width:windowWidth+'px'}">
			<view class="navbar-serach">
				<view class="navbar-serach_icon">
					<text class="iconfont icon-search"></text>
				</view>
				<view class="navbar-serach_text">
					un-app
				</view>
				
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
				statusBarHeight:20,
				navBarHeight:45,
				windowWidth:0
			};
		},
		created() {
			//手机信息
		 const info=	uni.getSystemInfoSync()
		 //状态栏高度
		 this.statusBarHeight = info.statusBarHeight
		 this.windowWidth=info.windowWidth
		 //#ifndef H5||APP-PLUS||MP-ALIPAY
		 //获取胶囊位置
		const menuButtonInfo = uni.getMenuButtonBoundingClientRect()
		let navBarHeight = (menuButtonInfo.bottom-info.statusBarHeight)+(menuButtonInfo.top-info.statusBarHeight)
		this.windowWidth = menuButtonInfo.left
		//#endif
		}
	}
</script>

<style lang="scss">
	
		@import '../../common/css/icons.css';
.navbar{
	.navbar-fixed{
		position: fixed;
		top: 0;
		left: 0;
		z-index: 99;
		width: 100%;
		background: $mk-base-color;
		height: 45px;
		.navbar-content{
			height: 45px;
			display: flex;
			justify-content: center;
			align-items: center;
			padding: 0 15px;
			box-sizing: border-box;
			.navbar-serach{
				display: flex;
				align-items: center;
				padding: 0 10px;
				width: 100%;
				height: 30px;
				border-radius:30px ;
				background-color: #fff;
				.navbar-serach_icon{
					
					margin-right: 10px;
				}
				.navbar-serach_text{
					font-size: 12px;
					color: #999;
				}
			} 
		}
	
	}

}
</style>
