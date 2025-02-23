<style scoped>
	.admin-page {
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
	    z-index: 3000;
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
		margin-bottom:60rpx;
	}
	
	.text-area{
		width: 100%; 
		text-align: left; 
		padding-left: 20rpx; 
		font-size: 28rpx; 
		font-weight: bold; 
		margin-top: 80rpx;
		padding-bottom: 30rpx; 
		margin-bottom:40rpx;
		display:flex;
		flex-direction:row;
	}
	
	.text{
		font-size:34rpx; 
		flex-grow: 1; /* 占据剩余空间，让行内剩余元素紧靠右侧 */
	}
	
	
	
	
	
	
	
	.backup-schedule {
		margin-top: 30rpx;
		padding: 20rpx;
		background-color: #f0f0f0;
		border-radius: 10rpx;
		text-align: center;
		width: 90%;
		height:300rpx;
		margin-bottom: 60rpx;
		display: flex;
		flex-direction: column;  /* 设置垂直排列 */
	}
	
	.backup-schedule-text {
		margin-top:40rpx;
		font-size: 35rpx;
		font-weight: 549;
		color: black;
		margin-bottom: 85rpx;
	}
	
	.backup-schedule-text1 {
		font-size: 20rpx;
		font-weight: 549;
		color: gray;
		line-height: 38rpx; /* 增加行距 */
	}
	
	
	
	
	
	
	
	/* “修改密码”按钮 */
	.modify-password-button{
		background-color: #555555;
		color: white; 
		width:200rpx;
		height:60rpx;
		border: none; 
		border-radius: 5px; 
		cursor: pointer; 
		line-height: 60rpx; 
		margin-top: 20rpx;
		text-align: center;
		font-size: 30rpx;
	}
/* 	.modify-password-button {
		background-color: #3388ff;
		color: white;
		width: 200rpx;
		height: 60rpx;
		border: none;
		border-radius: 15rpx;
		font-size: 28rpx;
		text-align: center;
		line-height: 60rpx;
		margin-top: -10rpx;
		margin-bottom:120rpx;
		cursor: pointer;
	}
	
	.modify-password-button:active{
		background-color: #0056b3; 
		border: none; 
	} */
	
	
	
	
	/* 修改密码弹窗 */
	.modify-password-modal {
	    position: fixed;
	    top: 0;
	    left: 0;
	    width: 100%;
	    height: 100%;
	    background-color: rgba(0, 0, 0, 0.5);  /* 遮罩层 */
	    display: flex;
	    align-items: center;
	    justify-content: center;
	    z-index: 1002;
	}
	
	/* 弹窗内容 */
	.modal-content1 {
	    width: 80%;
	    background-color: white;
	    border-radius: 10rpx;
	    padding: 30rpx;
	    text-align: center;
	    box-shadow: 0 4rpx 8rpx rgba(0, 0, 0, 0.2);
	    animation: slideIn 0.4s ease-out;
	}
	.userId-container {
	    display: flex;
	    align-items: center;  /* 垂直居中对齐输入框和按钮 */
	    margin-bottom: 40rpx;
		max-width: 533rpx;
	}
	
	/* 密码输入框和按钮容器 */
	.password-container {
	    display: flex;
	    align-items: center;  /* 垂直居中对齐输入框和按钮 */
	    margin-bottom: 20rpx;
	}
	
	/* 密码显示/隐藏按钮 */
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
	    outline: none;
	}
	
	.password-toggle-button:after{
		border:none;
	}
	
	.password-toggle-button .icon {
	    /* margin-right: 5rpx; */
		margin-left: 10rpx; /* 让图标和输入框之间有点间距 */
	}
	
	
	
	
	
	
	
	
	
	
	
	
	/* “登出”按钮 */
	.logout-button{
		background-color: black;
		color: white; 
		width:160rpx;
		height:70rpx;
		border: none; 
		border-radius: 10px; 
		cursor: pointer; 
		line-height: 70rpx; 
	}
	/* 登出确认弹窗 */
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
	
	
	
	
	
	
	
	.action-button {
	    background-color: lightseagreen;
	    color: white;
	    width: 440rpx;
	    height: 80rpx;
	    margin-bottom: 60rpx;
	    border-radius: 20rpx;
	    font-size: 28rpx;
	    text-align: center;
		line-height: 80rpx; /* 确保文字垂直居中 */
	}
	
	.action-button1 {
	    background-color: lightseagreen;
	    color: white;
	    width: 440rpx;
	    height: 80rpx;
	    margin-bottom: 180rpx;
	    border-radius: 20rpx;
	    font-size: 28rpx;
	    text-align: center;
		line-height: 80rpx; /* 确保文字垂直居中 */
	}
	
	.action-button2 {
	    background-color: #222222;
	    color: white;
	    width: 320rpx;
	    height: 80rpx;
	    margin-bottom: 120rpx;
	    border-radius: 20rpx;
	    font-size: 28rpx;
	    text-align: center;
		line-height: 80rpx; /* 确保文字垂直居中 */
	}

	
	
	
	
	
	
	/* 确认弹窗遮罩层 */
	.modal-overlay {
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background-color: rgba(0, 0, 0, 0.5);  
		display: flex;
		align-items: center;
		justify-content: center;
		z-index: 2000;  
	}
	
	/* 弹窗内容 */
	.modal-content {
		width: 80%;
		background-color: white;
		border-radius: 10rpx;
		padding: 30rpx;
		text-align: center;
		box-shadow: 0 4rpx 8rpx rgba(0, 0, 0, 0.2); 
		animation: slideIn 0.4s ease-out;  
	}
	.modal-content2 {
		width: 80%;
		background-color: white;
		border-radius: 10rpx;
		padding: 30rpx;
		text-align: center;
		box-shadow: 0 4rpx 8rpx rgba(0, 0, 0, 0.2); 
	}
	
	
	/* 按钮区域 */
	.modal-buttons {
	  display: flex;
	  justify-content: space-around;
	  margin-top: 35rpx;
	}
	
	/* 弹窗按钮 */
	.modal-button {
	  width: 120rpx;
	  height: 60rpx;
	  border-radius: 10rpx;
	  font-size: 28rpx;
	  text-align: center;
	  line-height: 60rpx;
	  cursor: pointer;
	}
	
	/* 确认按钮 */
	.confirm-button {
	  background-color: #28a745;  
	  background-color: #f44336;
	  color: white;
	}
	
	.confirm-button1 {
		background-color: #ff4d4f;
	    color: white;
	}
	
	/* 取消按钮 */
	.cancel-button {
	  background-color: #ccc; 
	  color: black;
	}
	
	/* 动画：从上到下滑入 */
	@keyframes slideIn {
	  0% {
		transform: translateY(-50rpx);
		opacity: 0;
	  }
	  100% {
	    transform: translateY(0);
	    opacity: 1;
	  }
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



	
	
	
	
	/* 底部的导航栏 */
	.footer-blank{
		height: 100rpx;
	}
	.footer {
	  display: flex;
	  flex-direction: row;
	  align-items: center;
	  justify-content: space-around;
	  position: fixed; /* 固定在页面底部 */
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
	<view class="admin-page">
		<view class="error-pop" :class="{ active: this.errorMessage }" :style="{ backgroundColor: errorPopBackgroundColor }">{{ this.errorMessage }}</view>
		<view class="header">
		    <text class="text">您好！尊敬的管理员</text>
			
			<button @click="handleLogout" class="logout-button">登出</button>
		</view>
		
		
		  <!-- 显示数据库备份周期 -->
		  <view class="backup-schedule">
		    <text class="backup-schedule-text">当前数据库备份周期：{{ this.backupSchedule }}  秒<br></text>
			<text class="backup-schedule-text1">在服务器正常运行的情况下<br>系统将自动进行数据库备份</text>
		  </view>
		
		<button class="action-button" @click="handleSetBackupSchedule">设置数据库备份周期</button>
		<!-- <button class="action-button1" @click="handleDownloadBackupFile">下载数据库备份文件</button> -->
		<button class="action-button1" @click="handleImmediateBackup">立即备份</button>

		<button @click="handleModifyPassword" class="modify-password-button">修改密码</button>






		<!-- 修改密码弹窗 -->
		<view v-if="showModifyPasswordModal" class="modify-password-modal">
		  <view class="modal-content1">
			<text class="info-label1">密码仅含字母、数字、下划线</text>
			
			<text class="info-label">输入当前管理员账号：</text>
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
			  <button class="modal-button confirm-button1" @click="confirmModifyPassword">确认</button>
			  <button class="modal-button cancel-button" @click="closeModifyPasswordModal">取消</button>
			</view>
		  </view>
		</view>
		
		
		
		
		
		
		
		<!-- 登出确认弹窗 -->
		<view v-if="showLogoutConfirm" class="logout-confirm-modal">
		  <view class="modal-content2">
		    <text>您确定要登出吗？</text>
		    <view class="modal-buttons">
		      <button class="modal-button confirm-button1" @click="confirmLogout">确定</button>
		      <button class="modal-button cancel-button" @click="closeLogoutConfirm">取消</button>
		    </view>
		  </view>
		</view>





		<!-- 设置备份周期的弹窗 -->
		<view v-if="showSetBackupScheduleModal" class="modal-overlay">
			<view class="modal-content">
				<text class="info-label">请输入新的备份周期 （ 单位：秒 ）：</text>
				<input v-model="newBackupSchedule" class="info-input" type="number" />
				<view class="modal-buttons">
					<button class="modal-button confirm-button1" @click="setBackupScheduleRequest">确认</button>
					<button class="modal-button cancel-button" @click="closeSetBackupScheduleModal">取消</button>
				</view>
			</view>
		</view>





		<!-- 下载数据库备份文件弹窗 -->
<!-- 		<view v-if="showDownloadConfirmationModal" class="modal-overlay">
		  <view class="modal-content">
			<text>您确定要下载数据库备份文件吗？</text>
			<view class="modal-buttons">
			  <button class="modal-button confirm-button" @click="downloadBackupFileRequest">确认</button>
			  <button class="modal-button cancel-button" @click="closeDownloadConfirmationModal">取消</button>
			</view>
		  </view>
		</view> -->
		
		<!-- 立即备份弹窗 -->
		<view v-if="showBackupConfirmationModal" class="modal-overlay">
		  <view class="modal-content">
			<text>您确定要立即进行数据库备份吗？</text>
			<view class="modal-buttons">
			  <button class="modal-button confirm-button" @click="immediateBackupRequest">确认</button>
			  <button class="modal-button cancel-button" @click="closeBackupConfirmationModal">取消</button>
			</view>
		  </view>
		</view>


		
		
		
		<!-- 底部导航栏 -->
		<!-- 添加一段空白挤占空间，防止footer底部导航栏遮挡住最下面的作业 -->
		<view class="footer-blank"></view>
		<view class="footer">
			<view class="footer-item" @click="goToHome">
				<view class="icon">📅</view>
				<view class="text">学期管理</view>
			</view>
			<view class="footer-item" @click="goToTeachers">
				<view class="icon">🧑‍🎓</view>
				<view class="text">教师管理</view>
			</view>
			<view class="footer-item" @click="goToProfile">
				<view class="icon">👤</view>
				<view class="text" style="color:#ff4d4f">系统管理</view>
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
			
			
			// 显示修改密码弹窗
			showModifyPasswordModal: false,
			showOldPassword: false,
			showNewPassword: false,
			showConfirmPassword: false,
			
			userId:"",
			oldPassword: "",
			newPassword: "",
			confirmNewPassword: "",
			
			
			
			// 显示登出确认弹窗
			showLogoutConfirm: false,

			
			
			
			backupSchedule: "",	// 备份周期
			newBackupSchedule: "",  // 用于存储用户输入的备份周期
			
			
			
			
			// 显示设置数据库备份周期弹窗
			showSetBackupScheduleModal: false,
			
			// 下载数据库备份文件弹窗
			showDownloadConfirmationModal: false, 
			
			// 立即备份弹窗
			showBackupConfirmationModal: false,   

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
		
		this.loadBackupSchedule();
	},
	
	
	
	methods: {
		// 向服务器获取备份周期(单位是分钟)
		loadBackupSchedule(){
			uni.request({
				url: `${this.apiUrl}/admin/queryBackupInterval`,
				method: 'GET',
				success: (res) => {
					if(res.data.code==='000'){
						this.backupSchedule=res.data.data/1000;
					}
					else{
						this.showError("网络错误，请稍后再试", "#ff4d4f");
						this.backupSchedule="Null";
					}
				},
				fail: (err) => {
					this.showError("网络错误，请稍后再试", "#ff4d4f");
				},
				complete: () => {
					uni.hideLoading();
				}
			});
		},
		
		
		
		
		
		
		// 修改密码
		handleModifyPassword(){
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
				// 账号字段
				userId:this.userId,
				// 密码字段
				oldPassword: this.oldPassword,
				newPassword: this.newPassword,
		    };
			
		    this.modifyPasswordRequest(passwordData);
		},
		  
		// 验证密码格式
		validatePasswordFormat(userId, oldPassword, newPassword, confirmNewPassword) {
			const passwordRegex = /^[A-Za-z0-9_]+$/;
			if (!userId || !oldPassword || !newPassword || !confirmNewPassword) {
				return { isValid: false, message: "账号和密码均不能为空" };
			}
			if (newPassword !== confirmNewPassword) {
				return { isValid: false, message: "两次输入的新密码不一致" };
			}
			if (!passwordRegex.test(newPassword) || !passwordRegex.test(oldPassword)) {
				return { isValid: false, message: "密码只含字母、数字、下划线" };
			}
			return { isValid: true, message: "" };
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
		closeModifyPasswordModal() {
		    this.showModifyPasswordModal = false;
			this.userId	= "";
		    this.oldPassword = "";
		    this.newPassword = "";
		    this.confirmNewPassword = "";
		    this.showOldPassword = false;
		    this.showNewPassword = false;
		    this.showConfirmPassword = false;
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









		// 登出
        handleLogout(){
			this.showLogoutConfirm = true;
		},
		
		closeLogoutConfirm() {
		    this.showLogoutConfirm = false;
		},
		confirmLogout() {
		    this.showLogoutConfirm = false;
		    uni.reLaunch({
		      url: "/pages/index/login",
		    });
		},
		
		
		
		
		
		
		
		// 设置数据库备份周期
		handleSetBackupSchedule() {
			if(!this.who){
				// console.log('Debug: this.who is', this.who); 
				this.showError("请先登录！");
				return;
			}
			this.showSetBackupScheduleModal = true;
		},
		closeSetBackupScheduleModal() {
			this.showSetBackupScheduleModal = false;
			this.newBackupSchedule = ""; // 清空输入框
		},
		setBackupScheduleRequest(){
			if(this.newBackupSchedule && !isNaN(this.newBackupSchedule) && this.newBackupSchedule > 0){
				const intervalInMilliseconds = this.newBackupSchedule * 1000;
				uni.showLoading({
					title: '正在修改中...', // 加载动画的提示文字
					mask: true // 阻止点击背景时关闭加载提示
				});
				uni.request({
					url: `${this.apiUrl}/admin/setBackupInterval?interval=${intervalInMilliseconds}`,
					method: 'GET',
					success: (res) => {
						if(res.data.code==='000'){
							this.showError("备份周期已更新", "#28a745");
							uni.showToast({
							    title: '更新成功',  // 提示的文本
							    icon: 'success',       // 可选值：'success', 'loading', 'none'，分别表示成功提示、加载提示和没有图标的提示
							    duration: 1000      // 提示框的显示时长，单位毫秒，默认2000ms
							});
						}
						else{
							this.showError("备份周期更新失败", "#ff4d4f");
						}
					},
					fail: (err) => {
						this.showError("网络错误，请稍后再试", "#ff4d4f");
					},
					complete: () => {
						uni.hideLoading();
						this.closeSetBackupScheduleModal();
						this.loadBackupSchedule();
					}
				});
			}
			else{
				this.showError("请输入有效数值", "#ff4d4f");
			}
		},
		
		
		
		
		
		
		
		// 下载数据库备份文件
		// handleDownloadBackupFile() {
		// 	this.showDownloadConfirmationModal = true;
		// },
		// closeDownloadConfirmationModal() {
		// 	this.showDownloadConfirmationModal = false;
		// },
		// downloadBackupFileRequest(){
		// 	if(this.downloadBackupFileResponse===true){
		// 		this.showError("数据库备份文件下载成功！", "#28a745");
		// 	}
		// 	else{
		// 		this.showError("数据库备份文件下载失败！", "#ff4d4f");
		// 	}
		// 	this.closeDownloadConfirmationModal();
		// },
		
		
		
		// 立即备份
		handleImmediateBackup() {
			if(!this.who){
				// console.log('Debug: this.who is', this.who); 
				this.showError("请先登录！");
				return;
			}
			this.showBackupConfirmationModal = true;
		},
		closeBackupConfirmationModal() {
			this.showBackupConfirmationModal = false;
		},
		immediateBackupRequest(){
			// 显示加载动画
			uni.showLoading({
				title: '正在备份中...', // 加载动画的提示文字
				mask: true // 阻止点击背景时关闭加载提示
			});
			uni.request({
				url: `${this.apiUrl}/admin/backupDatabase`, 
				method: 'GET',
				success: (res) => {
					if(res.data.code==='000'){
						this.showError("数据库备份成功！", "#28a745");
						uni.showToast({
						    title: '操作成功',  // 提示的文本
						    icon: 'success',       // 可选值：'success', 'loading', 'none'，分别表示成功提示、加载提示和没有图标的提示
						    duration: 1000      // 提示框的显示时长，单位毫秒，默认2000ms
						});
					}
					else{
						this.showError("数据库备份失败！", "#ff4d4f");
					}
				},
				fail: (err) => {
					this.showError("网络错误，请稍后再试", "#ff4d4f");
				},
				complete: () => {
					uni.hideLoading();
					this.closeBackupConfirmationModal();
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
		
		
		
		// 底部点击导航栏按钮切换页面
		// goToHome() {
		// 	uni.redirectTo({
		// 		url: `/pages/index/admin/admin1?id=${this.who}`  // 添加 id 参数
		// 	});

		// },
		// goToTeachers() {
		// 	uni.redirectTo({
		// 		url: `/pages/index/admin/admin2?id=${this.who}`  // 添加 id 参数
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
					url: `/pages/index/admin/admin1?id=${this.who}`  // 添加 id 参数
				});
			}
			else{
				uni.reLaunch({
					url: "/pages/index/admin/admin1"
				});
			}
		
		},
		goToTeachers() {
			if(this.who){
				uni.redirectTo({
					url: `/pages/index/admin/admin2?id=${this.who}`  // 添加 id 参数
				});
			}
			else{
				uni.reLaunch({
					url: "/pages/index/admin/admin2"
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


