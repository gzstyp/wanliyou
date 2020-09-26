<script>
	//应用生命周期
	//页面生命周期
	//组件生命周期
	export default {
		//应用生命周期,初始化完成后触发,全局仅触发一次
		onLaunch: function() {
			//登录操作,获取全局的变量
			console.log('App Launch')
		},
		//应用启动或从后台进入前台的时候触发
		onShow: function() {
			console.log('App Show')
		},
		//从前台进入后台的时候触发
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
</style>
