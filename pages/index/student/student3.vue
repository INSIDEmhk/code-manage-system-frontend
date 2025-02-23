<style scoped>
	.student-page {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		width:637.5rpx;
		margin: auto; /* 自动居中 */
	}
	
	
	
	.error-pop {
	    position: fixed;
		left: 20%; /* 水平居中 */
	    top: -500rpx; /* 默认隐藏在顶部以外 */
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
	
	
	
	
	
	
	.header{
		padding-top:80rpx;
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: center;
		/* border: 1px solid green; */
		width: 100%; 
		margin-bottom:25rpx;
	}
	
	.text{
		font-size:35rpx; 
		flex-grow: 1; /* 占据剩余空间，让行内剩余元素紧靠右侧 */
	}
	
	
	
	
	
	
	/* “修改密码”按钮 */
	.modify-password-button{
/* 		background-color: gray;
		color: white; 
		width:220rpx;
		height:70rpx;
		border: none; 
		border-radius: 10px; 
		cursor: pointer; 
		line-height: 70rpx; 
		margin-right:50rpx; */
		background-color: #555555;
		color: white; 
		width:200rpx;
		height:60rpx;
		border: none; 
		border-radius: 5px; 
		cursor: pointer; 
		line-height: 60rpx; 
		margin-top: -16rpx;
		text-align: center;
		font-size: 30rpx;
	}
	
	/* “登出”按钮 */
	.logout-button{
		background-color: black;
		color: white; 
		width:180rpx;
		height:70rpx;
		border: none; 
		border-radius: 10px; 
		cursor: pointer; 
		line-height: 70rpx; 
	}
	
	
	
	.backup-schedule {
		margin-top: 30rpx;
		padding: 20rpx;
		background-color: #f0f0f0;
		border-radius: 10rpx;
		text-align: center;
		width: 90%;
		height:270rpx;
		margin-bottom: 50rpx;
		display: flex;
		flex-direction: column;  /* 设置垂直排列 */
	}
	
	.backup-schedule-text {
		margin-top:40rpx;
		font-size: 35rpx;
		font-weight: 549;
		color: black;
		margin-bottom: 65rpx;
	}
	
	.backup-schedule-text1 {
		font-size: 20rpx;
		font-weight: 549;
		color: gray;
		line-height: 38rpx; /* 增加行距 */
	}
	
	
	
	
	
	
	/* 学生基本信息 */
	.info-container {
		width: 100%;
		margin-bottom: 60rpx;
	}

	.info-item {
		margin-bottom: 30rpx;
	}
	
	.info-label1 {
		font-size: 35rpx;
		font-weight: bold;
		margin-bottom: 80rpx;
		display: block;
		text-align: left;
	}

	.info-label {
		font-size: 28rpx;
		font-weight: bold;
		margin-bottom: 10rpx;
		display: block;
		text-align: left;
	}

	.info-input {
		box-sizing: border-box; 
		width: 100%;
		height: 60rpx;
		border: 1px solid #ccc;
		border-radius: 10rpx;
		padding: 0 10rpx;
		font-size: 24rpx;
		outline: none;
		text-align: left; /* 左对齐文本 */
	}
	
	
	
	
	
	
    /* “保存信息”按钮 */
	.save-button {
		background-color: #007bff;
		color: white;
		width: 200rpx;
		height: 60rpx;
		border: none;
		border-radius: 10rpx;
		font-size: 28rpx;
		text-align: center;
		line-height: 60rpx;
		margin-top: 20rpx;
		cursor: pointer;
	}
	
	.save-button:active{
		background-color: #0056b3; 
		border: none; 
	}
	
	
	
	
	
	
	 /* "登出"确认弹窗 */
	.logout-confirm-modal {
	    position: fixed;
	    top: 0;
	    left: 0;
	    width: 100%;
	    height: 100%;
	    background-color: rgba(0, 0, 0, 0.5);
	    display: flex;
	    align-items: center;
	    justify-content: center;
	    z-index: 1001;
	}
	 
	 /* “修改密码”弹窗 */
	.modify-password-modal {
	    position: fixed;
	    top: 0;
	    left: 0;
	    width: 100%;
	    height: 100%;
	    background-color: rgba(0, 0, 0, 0.5);
	    display: flex;
	    align-items: center;
	    justify-content: center;
	    z-index: 1002;
	}
	 
	 
	
	.userId-container {
	    display: flex;
	    align-items: center;  /* 垂直居中对齐输入框和按钮 */
	    margin-bottom: 40rpx;
		max-width: 533rpx;
	}
	
	
	/* 修改密码输入框和图标按钮的容器 */
	.password-container {
	    display: flex;
	    align-items: center; /* 垂直居中对齐输入框和按钮 */
	    margin-bottom: 20rpx; /* 增加每个输入框和按钮之间的间距 */
	}
	
	/* 修改密码显示/隐藏按钮 */
	.password-toggle-button {
	    background-color: transparent;
	    border: none;
	    font-size: 28rpx;
	    color: #007bff; 
	    cursor: pointer; 
	    padding: 5rpx 10rpx; 
	    border-radius: 5rpx; 
	    display: inline-flex;
	    align-items: center;
	    justify-content: center;
	    transition: color 0.3s ease; 
		outline:none;
	}
	
	.password-toggle-button:after{
		border:none;
	}
	
	.password-toggle-button .icon {
	    /* margin-right: 5rpx; */
		margin-left: 10rpx; /* 让图标和输入框之间有点间距 */
	}

	 
	 
	 
	 
	 
    /* 弹窗 */
	.modal-content {
	    width: 80%;
	    background-color: white;
	    border-radius: 10rpx;
	    padding: 30rpx;
	    text-align: center;
	    box-shadow: 0 4rpx 8rpx rgba(0, 0, 0, 0.2);
	}
	
	.modal-content1 {
		width: 80%;
		background-color: white;
		border-radius: 10rpx;
		padding: 30rpx;
		text-align: center;
		box-shadow: 0 4rpx 8rpx rgba(0, 0, 0, 0.2);
		animation: slideIn1 0.4s ease-out; /* 使用动画 */
	}
	 
	.modal-buttons {
	    display: flex;
	    justify-content: space-around;
	    margin-top: 20rpx;
	}
	 
	.modal-button {
	    width: 120rpx;
	    height: 60rpx;
	    border-radius: 10rpx;
	    font-size: 28rpx;
	    text-align: center;
	    line-height: 60rpx;
	    cursor: pointer;
	}
	 
	/* 弹窗的红色“确认”按钮 */
	.confirm-button {
		background-color: #ff4d4f;
	    color: white;
	}
	 
	/* 弹窗的白色“取消”按钮 */ 
	.cancel-button {
	    background-color: #ccc;
	    color: black;
	}
	
	
	
	
	
	@keyframes slideIn1 {
	    0% {
	        transform: translateY(-80rpx); 
	        opacity: 0;
	    }
	    100% {
	        transform: translateY(0); 
	        opacity: 1;
	    }
	}
	
	
	
	
	
	/* 底部的导航栏 */
	.footer-blank{
		height: 100rpx;
	}
	
	.footer {
	  display: flex;
	  flex-direction: row;
	  align-items: center;
	  justify-content: space-around;
	  position: fixed; 
	  bottom: 0;
	  left: 0;
	  width: 100%;
	  height: 100rpx;
	  background-color: #f9f9f9;
	  border-top: 1px solid #e0e0e0;
	  box-shadow: 0 -2rpx 4rpx rgba(0, 0, 0, 0.1);
	}
	
	.footer-item {
	  display: flex;
	  flex-direction: column;
	  align-items: center;
	  justify-content: center;
	  flex: 1;
	  color: #666666;
	  font-size: 28rpx;
	}
	
	.footer-item .icon {
	  font-size: 36rpx;
	  margin-bottom: 5rpx;
	}
	
	.footer-item .text {
	  font-size: 24rpx;
	}
</style>






<template>
	<view class="student-page">
		<view class="error-pop" :class="{ active: this.errorMessage }" :style="{ backgroundColor: errorPopBackgroundColor }">{{ this.errorMessage }}</view>
		<view class="header">
		    <text class="text">基本信息</text>
			
			<button @click="handleLogout" class="logout-button">登出</button>
		</view>
		
		<view class="backup-schedule">
			<text class="backup-schedule-text">学生账号由管理员统一分发<br></text>
			<text class="backup-schedule-text1">如有疑问或需要变更账号信息<br>请前往官网获取管理员联系方式</text>
		</view>
		
		
		<!-- 学生基本信息 -->
		<view class="info-container">
			<view class="info-item">
				<text class="info-label">学号：</text>
				<input class="info-input" type="text" :value="this.studentInf[0].studentId" disabled   v-if="studentInf && studentInf[0] && !studentInf[1]"/>
			</view>
			<view class="info-item">
				<text class="info-label">姓名：</text>
				<input class="info-input" type="text" :value="this.studentInf[0].name" disabled   v-if="studentInf && studentInf[0] && !studentInf[1]"/>
			</view>
			<view class="info-item">
				<text class="info-label">性别：</text>
				<input class="info-input" type="text" :value="this.studentInf[0].sex" disabled   v-if="studentInf && studentInf[0] && !studentInf[1]"/>
			</view>
			<view class="info-item">
				<text class="info-label">电话号码：</text>
				<input class="info-input" type="text" v-model="this.studentInf[0].email"  disabled  ref="phoneNumberInput"   v-if="studentInf && studentInf[0] && !studentInf[1]"/>
			</view>
			<view class="info-item">
				<text class="info-label">邮箱地址：</text>
				<input class="info-input" type="text" v-model="this.studentInf[0].phoneNumber" disabled  ref="mailInput"   v-if="studentInf && studentInf[0] && !studentInf[1]"/>
			</view>
		</view>
		
		
		
		<!-- “保存信息”按钮 -->
		<!-- <button class="save-button" @click="handleModifyStudentInformation" :disabled="isSubmitting">保存信息</button> -->
		<button @click="handleModifyPassword" class="modify-password-button">修改密码</button>


		<!-- 底部导航栏 -->
		<view class="footer-blank"></view>
		<view class="footer">
			<view class="footer-item" @click="goToHome">
				<view class="icon">🏠</view>
				<view class="text">首页</view>
			</view>
			<view class="footer-item" @click="goToCourses">
				<view class="icon">📘</view>
				<view class="text">课程</view>
			</view>
			<view class="footer-item" @click="goToProfile">
				<view class="icon">👤</view>
				<view class="text" style="color:#ff4d4f">我的</view>
			</view>
		</view>
		
		
		
		<!-- “修改密码”弹窗 -->
		<view v-if="showModifyPasswordModal" class="modify-password-modal">
		    <view class="modal-content1">
				<text class="info-label1">密码仅含字母、数字、下划线</text>
				
				
				<text class="info-label">输入当前学生账号：</text>
				<view class="userId-container">
					<input v-model="userId" class="info-input" />
				</view>
				
				
				<!-- 输入旧密码 -->
				<text class="info-label">输入旧密码：</text>
				<view class="password-container">
					<input :type="showOldPassword ? 'text' : 'password'" v-model="oldPassword" class="info-input" />
					<button @click="toggleOldPasswordVisibility" class="password-toggle-button">
						<text class="icon">{{ showOldPassword ? '🔒' : '👁️' }}</text>
					</button>
				</view>
				
				<!-- 输入新密码 -->
				<text class="info-label">输入新密码：</text>
				<view class="password-container">
					<input :type="showNewPassword ? 'text' : 'password'" v-model="newPassword" class="info-input" />
					<button @click="toggleNewPasswordVisibility" class="password-toggle-button">
						<text class="icon">{{ showNewPassword ? '🔒' : '👁️' }}</text>
					</button>
				</view>
				
				<!-- 输入第二遍新密码 -->
				<text class="info-label">再输入一遍新密码：</text>
				<view class="password-container">
					<input :type="showConfirmPassword ? 'text' : 'password'" v-model="confirmNewPassword" class="info-input" />
					<button @click="toggleConfirmPasswordVisibility" class="password-toggle-button">
						<text class="icon">{{ showConfirmPassword ? '🔒' : '👁️' }}</text>
					</button>
				</view>
				
                <!-- “确认”按钮和“关闭”按钮 -->
		        <view class="modal-buttons">
		            <button class="modal-button confirm-button" @click="confirmModifyPassword">确认</button>
		            <button class="modal-button cancel-button" @click="closeModifyPasswordModal">取消</button>
		        </view>
		    </view>
		</view>



		<!-- “登出”确认弹窗 -->
		<view v-if="showLogoutConfirm" class="logout-confirm-modal">
		    <view class="modal-content">
		        <text>您确定要登出吗？</text>
		        <view class="modal-buttons">
					<button class="modal-button confirm-button" @click="confirmLogout">确定</button>
		            <button class="modal-button cancel-button" @click="closeLogoutConfirm">取消</button>
		        </view>
		    </view>
		</view>
	</view>
</template>






<script>
	import { config } from '../../../config'; // 导入 config.js 文件
	
	
export default {
    data() {
    	return {
			apiUrl: `http://${config.host}:${config.port}`, // 使用配置的host和port
			
			
			who:"",
			
			
			
			// 顶部弹窗
			errorMessage: "", 
			errorPopBackgroundColor: '#ff4d4f', // 错误弹窗背景颜色
			timeoutId: null,
			
			
			
			// “修改密码”弹窗
			showModifyPasswordModal: false, 
			showOldPassword: false,
			showNewPassword: false,
			showConfirmPassword: false,
			
			
			userId:"",
			oldPassword: "", 
			newPassword: "", 
			confirmNewPassword: "", 
			
			
			
			// “登出”确认弹窗
			showLogoutConfirm: false, 
			
			
    		// 学生基本信息
			studentInf:"",
			
			

    	};
    },
	
	
	
	
	
	
	onLoad(query) {
		console.log(query.id);
		this.who=query.id;
		
		
		if(!this.who){
			// console.log('Debug: this.who is', this.who); 
			this.showError("请先登录！");
			uni.reLaunch({
				// (url后期需要修改！！！)
			    url: "/pages/index/login"
			});
			return;
		}
		
		
		this.loadStudentInformation(); 
	},
	
	
	
	
	
	
	methods: {
		// 向服务器获取学生基本信息
		loadStudentInformation() {
			// if(!this.who){
			// 	// console.log('Debug: this.who is', this.who); 
			// 	this.showError("网络错误，请稍后再试");
			// 	return;
			// }
			uni.request({
				url: `${this.apiUrl}/api/queryStudentByFactor`, 
				method: 'POST',
				data:{
					"studentId": this.who
				},
				success: (res) => {
					 // console.log(res);
					if (res.data.code === '000') {
						this.studentInf=res.data.data;
						// console.log(this.studentInf[0]);
					} 
					else {
						this.showError(res.data.info); // 显示错误信息
					}
				},
				fail: () => {
					this.showError("网络错误，请稍后再试");
				}
			});
		},
		
		
		
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
		
		
		
		
		



		// “修改密码”按钮
		handleModifyPassword() {
			// if(!this.who){
			// 	return;
			// }
			if(!this.who){
				// console.log('Debug: this.who is', this.who); 
				this.showError("请先登录！");
				return;
			}
		    this.showModifyPasswordModal = true; 
		},
		
		confirmModifyPassword() {
			const validation = this.validatePasswordFormat(this.userId, this.oldPassword, this.newPassword, this.confirmNewPassword);
			if (!validation.isValid) {
				this.showError(validation.message);
				return;
			}
			
			const passwordData = {
				userId:this.userId,
				oldPassword: this.oldPassword,   
				newPassword: this.newPassword,            
			};
			
			this.modifyPasswordRequest(passwordData)
		},
		
		closeModifyPasswordModal() {
			// 关闭密码修改弹窗
		    this.showModifyPasswordModal = false;
			// 清空密码输入框
			this.userId="",
			this.oldPassword = "";
			this.newPassword = "";
			this.confirmNewPassword = "";
			// 重置密码显示状态
			this.showOldPassword = false;
			this.showNewPassword = false;
			this.showConfirmPassword = false;
		},
		
		validatePasswordFormat(userId, oldPassword, newPassword, confirmNewPassword){
			const passwordRegex = /^[A-Za-z0-9_]+$/;
			if (!userId || !oldPassword || !newPassword || !confirmNewPassword) {
				return { isValid: false, message: "账号和密码均不能为空" };
			}
			else if (newPassword !== confirmNewPassword) {
				return { isValid: false, message: "两次输入的新密码不一致" };
			}
			else if (!passwordRegex.test(newPassword)||!passwordRegex.test(oldPassword)) {
				return { isValid: false, message: "密码只含字母、数字、下划线" };
			}
			return { isValid: true, message: "" };
		},
		
		modifyPasswordRequest(passwordData){
			// 向服务器发送 POST 请求修改密码
			uni.showLoading({
			    title: '正在修改密码...', // 加载动画的提示文字
			    mask: true // 阻止点击背景时关闭加载提示
			});
			uni.request({
				url: `${this.apiUrl}/changePassword`, 
			    method: 'POST',
			    data: passwordData, 
			    success: (res) => {
					if (res.data.code === '000') {
						this.showError("密码修改成功！", "#28a745");
						uni.showToast({
						    title: '修改成功',  // 提示的文本
						    icon: 'success',       // 可选值：'success', 'loading', 'none'，分别表示成功提示、加载提示和没有图标的提示
						    duration: 1000      // 提示框的显示时长，单位毫秒，默认2000ms
						});
					} 
					else {
						// 如果失败，显示错误信息
						this.showError(res.data.info);
					}
			    },
			    fail: () => {
					// 请求失败处理
					this.showError("网络错误，请稍后再试");
			    },
				complete: () => {
					this.closeModifyPasswordModal();
					// 隐藏加载动画
					uni.hideLoading();
				}
			});
			
			
			

		},
		
		toggleOldPasswordVisibility() {
		  this.showOldPassword = !this.showOldPassword;
		},
		toggleNewPasswordVisibility() {
		  this.showNewPassword = !this.showNewPassword;
		},
		toggleConfirmPasswordVisibility() {
		  this.showConfirmPassword = !this.showConfirmPassword;
		},

		
		
		
		
		
		
		
		
		
		
		
	    // “登出”按钮
	    handleLogout() {
	        this.showLogoutConfirm = true;
	    },
		
		confirmLogout() {
		    this.showLogoutConfirm = false;
			// 使用reLaunch避免通过后退返回到当前页
			uni.reLaunch({
				// (url后期需要修改！！！)
			    url: "/pages/index/login"
			});

		},	
		
	    closeLogoutConfirm() {
	        this.showLogoutConfirm = false;
	    },

		
		
		
		
		
		// 底部导航栏按钮
		// goToHome() {
		// 	uni.redirectTo({
		// 		url: `/pages/index/student/student1?id=${this.who}`  // 添加 id 参数
		// 	});

		// },
		// goToCourses() {
		// 	uni.redirectTo({
		// 		url: `/pages/index/student/student2?id=${this.who}`  // 添加 id 参数
		// 	});

		// },
		// goToProfile() {
		// 	uni.pageScrollTo({
		// 		scrollTop: 0, // 滚动到页面顶部
		// 		duration: 500, // 滚动动画的持续时间（毫秒）
		// 	});
		// },
		goToHome() {
			if(this.who){
				uni.redirectTo({
					url: `/pages/index/student/student1?id=${this.who}`  // 添加 id 参数
				});
			}
			else{
				uni.reLaunch({
					url: "/pages/index/student/student1"
				});
			}
		},
		goToCourses() {
			if(this.who){
				uni.redirectTo({
					url: `/pages/index/student/student2?id=${this.who}`  // 添加 id 参数
				});
			}
			else{
				uni.reLaunch({
					url: "/pages/index/student/student2"
				});
			}
		},
		goToProfile() {
			uni.pageScrollTo({
				scrollTop: 0, // 滚动到页面顶部
				duration: 500, // 滚动动画的持续时间（毫秒）
			});
		},
	},
};
</script>