<template>
	<view class="content">
		<btn color="#f00" @myEvent="custEvent">使用vue的自定义事件,子组件往父组件传事件</btn>
	</view>
</template>

<script>
	import btn from '../../components/btn.vue'
	export default {
		components:{
			btn
		},
		data() {
			return {
				title: '足疗店'
			}
		},
		//监听页面加载,页面标签还没渲染完成
		onLoad() {
			//api的使用示例
			uni.getSystemInfo({
				success(res) {
					console.info('成功的回调');
				},
				fail(err) {
					console.info('失败的回调');
				},
				complete(res) {
					console.info('不管是成功还是失败都会回调');
				}
			})
		},
		//它和onLoad是相反的,监听页面卸载,用于关闭当前页面打开新页面
		onUnload() {
			console.info('监听页面卸载,用于关闭当前页面打开新页面');
		},
		//监听页面初始渲染完成,页面标签已渲染完成
		onReady() {
			//TODO 如果渲染速度快，会在页面进入动画完成前触发
		},
		//监听页面显示,即每次页面显示时都触发,页面跳转
		onShow() {
			console.info('监听页面显示,即每次页面显示时都触发,它优先于onTabItemTap,但有些可能是没有onTabItemTap事件');
		},
		//监听页面隐藏,每次页面隐藏都触发
		onHide() {
			console.info('每次页面隐藏都触发');
		},
		onTabItemTap(item) {
			console.info('首页的onTabItemTap');
			console.info(item);
		},
		methods: {
			custEvent(value){
				console.info('我是父页面的点击事件[监听回调函数],并收到了参数:' + value);
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
