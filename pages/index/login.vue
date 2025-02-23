<style scoped>
	.login-page {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		margin:auto;
	}
	
	
	
	.error-pop {
	    position: fixed;
		left: 20%; 
	    top: -500rpx; 
		width:60%;
	    background-color: #ff4d4f;
	    color: white;
	    font-size: 32rpx;
	    text-align: center;
	    line-height: 100rpx;
	    height: 100rpx;
	    z-index: 2000;
	    box-shadow: 0rpx 8rpx 12rpx rgba(0, 0, 0, 0.1);
	    transition: top 0.3s ease; 
		border-radius:20rpx;
	}
	
	.error-pop.active {
	    top: 105rpx; 
	}






	.logo {
		height: 500rpx;
		width: 630rpx;
		margin-top: 60rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
		background-size: cover; 
	}






	.login-form {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		margin-bottom:40rpx;
	}
	
	.input-row {
		display: flex;
		flex-direction: row;
		align-items: center; 
		width: 100%; 
		margin-bottom: 40rpx;
	}
	
	.input-row p {
		font-size: 36rpx;
		margin: 0; 
		text-align: right;
		margin-right: 20rpx; 
		white-space: nowrap; 
		padding-bottom:40rpx;
	}
	
	.input{
		width: 60%; 
		height: 70rpx; 
		margin-bottom: 40rpx; 
		padding: 0 20rpx; 
		border: 1px solid #ccc;
		border-radius: 10rpx; 
		font-size: 28rpx; 
		outline: none; 
	}

	
	
	
	
	
	.login-button{
		background-color: #007bff;
		color: white; 
		width:230rpx;
		height:70rpx;
		border: none; 
		border-radius: 10px; 
		cursor: pointer; 
		line-height: 70rpx; 
	}
	
	.login-button:active{
		background-color: #0056b3; /* 点击按钮时的背景色 */
		border: none; 
	}
</style>






<template>
	<view class="login-page">
		<view>
			<view class="error-pop" :class="{ active: this.errorMessage }" :style="{ backgroundColor: errorPopBackgroundColor }">{{ this.errorMessage }}</view>
			<!-- （src后期需要修改！！！） -->
			<image class="logo" src="/static/logo.jpg"></image>
			<view class="login-form">
				<view class="input-row"><p>账号：</p><input class="input" type="text" placeholder="请输入账号" v-model="username"/></view>
				<view class="input-row"><p>密码：</p><input class="input" type="password"  placeholder="请输入密码" v-model="password"/></view>
			</view>
			<button class="login-button"  @click="handleLogin" >登录</button>
		</view>	
	</view>
</template>






<script>
	import { config } from '../../config'; // 导入 config.js 文件
	
	
	export default {
		data() {
			return {
				 apiUrl: `http://${config.host}:${config.port}`, // 使用配置的host和port
				 
				 
				// 顶部弹窗
				errorMessage: "", 
				errorPopBackgroundColor: '#ff4d4f', // 错误弹窗背景颜色
				timeoutId: null,
				
				
				// 登录表单
				username: "",  
				password: "",     
			}
		},
		
		
		
		
		
		
		onLoad() {

		},
		
		
		
		
		
		
		methods: {
			// 顶部弹窗
			showError(message, color = "#ff4d4f") {
				this.errorMessage = message; // 显示错误信息
				this.errorPopBackgroundColor = color; // 设置弹窗背景色
				if (this.timeoutId) {
					clearTimeout(this.timeoutId); // 清除之前的定时器
				}
				this.timeoutId = setTimeout(() => {
					this.errorMessage = ""; // 隐藏错误信息
					this.timeoutId = null; // 清除定时器
				}, 1200); // 1.2秒后隐藏错误信息
			},
				
			
			
			
			
			
			// 点击“登录”按钮
			handleLogin() {
				// 本地校验账号和密码是否符合正确格式
				if (!this.validate_Username_Password_Format()) {
					return;
				}	
				
				// 构建账号密码表单
				const loginData = {
					userId: this.username.trimEnd(),   
					password: this.password,            
				};
				
				// 向服务器发起登录请求
				this.loginRequest(loginData);
			},
			
			
			
			
			
			
			// 本地校验账号密码是否符合正确格式
			validate_Username_Password_Format(){
				const usernameRegex = /^[a-zA-Z0-9]+$/;
				const passwordRegex = /^[A-Za-z0-9_]+$/;
				if (!this.username.trim()||!this.password.trim()) {
					this.showError("账号和密码不能为空");
					return false;
				}
				else if (!usernameRegex.test(this.username.trimEnd())) {
					this.showError("账号只能包含字母和数字");
					return false;
				}
				else if (!passwordRegex.test(this.password)) {
					this.showError("密码只能包含字母、数字和下划线");
					return false;
				}	
				return true;
			},
			
			
			
			
			
			
			// 向服务器发起“登录”请求，并接受服务器的响应(loginResponse)
			loginRequest(loginData) {
				uni.showLoading({
					title: '正在登陆中...', // 加载动画的提示文字
					mask: true // 阻止点击背景时关闭加载提示
				});
				uni.request({
					url: `${this.apiUrl}/login`, 
					method: 'POST',
					data: loginData,
					success: (res) => {
						// console.log(res);  // 调试输出
						if (res.data.code === '000') {
							// 登录成功，根据返回的type跳转页面
							const userType = res.data.data;
							this.navigateToPage(userType);
							uni.showToast({
							    title: '登录成功',  // 提示的文本
							    icon: 'success',       // 可选值：'success', 'loading', 'none'，分别表示成功提示、加载提示和没有图标的提示
							    duration: 1000      // 提示框的显示时长，单位毫秒，默认2000ms
							});
						} 
						else {
							// 登录失败，显示错误信息
							this.showError(res.data.info);
						}
					},
					fail: () => {
						this.showError("网络错误，请稍后再试");
					},
					complete: () => {
						uni.hideLoading();
					}
				});
				
			},
			
			
			
			
			
			
			// 根据服务器的信息跳转到账号对应的页面：学生/教师/管理员
			navigateToPage(userType){
				console.log('登录id',this.username);
				if (userType === "student") {
					uni.redirectTo({
					  url: `/pages/index/student/student1?id=${this.username}`
					});
				} 
				else if (userType === "teacher") {
					uni.redirectTo({
					  url: `/pages/index/teacher/teacher1?id=${this.username}`
					});
				} 
				else if (userType === "admin") {
					uni.redirectTo({
					  url: `/pages/index/admin/admin1?id=${this.username}`
					});
				}  
			},
		}
	}
</script>