<template>
	<view class="view-root" :style="{color:color}" @click="onClick">
		<slot>登录</slot><!-- 有值就被替换,没值就显示默认值 -->
	</view>
</template>

<script>
	export default{
		props : {
			color : {
				type : String,
				default : '#000'
			}
		},
		data() {
			return {}
		},
		//在实例初始化之后，数据观测 (data observer) 和 event/watcher 事件配置之前被调用
		beforeCreate() {
			
		},
		// 在实例创建完成后被立即调用,挂载阶段还没开始，$el 属性目前不可见。
		created() {
			
		},
		methods : {
			onClick(){
				console.info('子组件被点击了');
				//emit-->发出，放射，发射
				this.$emit('myEvent',this.color);//父组件的事件的监听回调,其中myEvent是事件名,第二个参数是该事件名需要的参数
			}
		}
	}
</script>

<style scoped>
	.view-root{
		padding: 12rpx;
		border-radius: 6rpx;
		border:1px solid #eee;
	}
</style>
