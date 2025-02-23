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
	
	
	
	
	
	
	.text-area{
		width: 100%; 
		text-align: left; 
		padding-left: 20rpx; 
		font-size: 28rpx; 
		font-weight: bold; 
		margin-top: 80rpx;
		padding-bottom: 30rpx; 
		margin-bottom:20rpx;
		display:flex;
		flex-direction:row;
	}
	
	.text{
		font-size:35rpx; 
		flex-grow: 1; /* 占据剩余空间，让行内剩余元素紧靠右侧 */
	}
	
	
	
	
	
	
	
	.button-container {
	    width: 100%;       
		display:flex;
		flex-direction: row;
		/* border:1px solid black; */
		justify-content: space-between;
		margin-bottom:15rpx;
	}

	.createTeacher-button {
		cursor: pointer;
		border: none;
		outline:none;
		background-image: url('/static/createTeacherButton.png');
		height:90rpx;
		width:140rpx;
		background-size: cover;
		background-size: contain;
		background-position: center; 
		/* border:1px solid black; */
		margin:0;
		margin-left:10rpx;
	}
	
	.createTeacher-button:after {
		border:none;
	}
	
	.bulkImport-button {
		cursor: pointer;
		border: none;
		outline:none;
		background-image: url('/static/bulkImportButton.png'); 
		height:90rpx;
		width:210rpx;
		background-size: cover;
		background-position: center; 
		background-size: contain;
		/* border:1px solid black; */
		margin-left: auto;
		margin:0;
		margin-left:20rpx;
		transform: translateX(0rpx) translateY(6rpx); /* 向右平移，向下平移 */
	}
	
	.bulkImport-button:after {
		border:none;
	}
	
	
	
	
	
	
	
	
	
	
	
	/* 弹窗样式 */
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
	  z-index: 2000; /* 保证遮罩层的 z-index 比底部导航栏高 */
	}
	
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
	  animation: slideIn1 0.5s ease forwards;  /* 滑入动画 */
	}
	
	.modal-buttons {
	  display: flex;
	  justify-content: space-around;
	  margin-top: 35rpx;
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
	
	.confirm-button {
		/* #28a745 */
	  background-color: #f44336;
	  color: white;
	}
	
	.confirm-button1 {
		/* #28a745 */
	  background-color: #28a745;
	  background-color: #f44336;
	  color: white;
	}
	
	.cancel-button {
	  background-color: #ccc;
	  color: black;
	}

	.info-label {
		font-size: 28rpx;
		margin-bottom: 10rpx;
		display: flex; 
		justify-content: flex-start; /* 左对齐 */
	}
	.info-input {
		width: 95%;
		height: 38rpx; /* 设置输入框的高度 */
		/* min-height:0rpx; */
		padding: 10rpx;
		font-size: 28rpx;
		border-radius: 10rpx;
		margin-bottom: 20rpx;
		border:1px solid lightgray;
		margin-top:15rpx;
		margin-bottom:60rpx;
		text-align: left;
	}


	
	
	
	
	
	
	
	
	
	.teacher-list-section {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: flex-start; 
		width: 100%;
		padding: 10rpx;
		box-sizing: border-box; 
		border:1px solid gray;
		border-radius: 20rpx;
		padding-left:15rpx;
		padding-right:15rpx;
		min-height:180rpx;
		margin-bottom: 20rpx;
	}
	
	.teacher-item {
		width: 100%; 
		margin-top:20rpx;
		margin-bottom: 30rpx;
		animation: slideIn 0.6s ease forwards;  /* 滑入动画 */
	}
	
	.teacher-card {
		display: flex;
		flex-direction: column;  
		background-color: #f9f9f9; 
		padding: 20rpx; 
		border-radius: 10rpx; 
		box-shadow: 0 2rpx 6rpx rgba(0, 0, 0, 0.1); 
		border: 1px solid #ddd; 
		height:190rpx;
		border:none;
	}
	
	.teacher-name {
		font-size: 34rpx;
		transform: translateX(0rpx) translateY(10rpx); 
	}
	
	.teacher-teacherId {
		font-size: 20rpx;
		transform: translateX(0rpx) translateY(30rpx); 
		margin-bottom: 10rpx;
	}
	
	.teacher-email {
		font-size: 20rpx;
		transform: translateX(0rpx) translateY(24rpx); 
	}
	
	
	.delete-button {
	    width: 160rpx;
	    height: 50rpx;
	    background-color: #f44336;
	    color: white;
	    font-size: 24rpx;
	    border-radius: 12rpx;
	    display: flex;
	    justify-content: center;
	    align-items: center;
	    cursor: pointer;
		margin-right:0;
	}
	
	.delete-button:hover {
	    background-color: #e53935;
	}
	
	
	
	
	
	

	/* 从上到下滑入 */
	@keyframes slideIn {
		0% {
			transform: translateY(-20rpx);  
			opacity: 0;  
		}
		100% {
			transform: translateY(0);  
			opacity: 1;  
		}
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
		
		
		<view class="text-area">
			<text class="text">教师信息展示</text>
		</view>
		
		
		<view class="button-container">
			<button class="createTeacher-button" @click="openCreateTeacherModal"></button>
			<!-- <button class="bulkImport-button" @click="openFirstConfirmationModal"></button> -->
		</view>
		
		
		
		
		
		<!-- 创建教师弹窗 -->
		<view v-if="showCreateTeacherModal" class="modal-overlay">
		  <view class="modal-content1">
			<text class="info-label">新教师姓名：</text>
			<input v-model="newTeacherName" class="info-input" />
			<text class="info-label">新教师邮箱：</text>
			<input v-model="newTeacherEmail" class="info-input" />
			<!-- 弹窗操作按钮 -->
			<view class="modal-buttons">
			  <button class="modal-button confirm-button1" @click="handleCreateTeacher">确认</button>
			  <button class="modal-button cancel-button" @click="closeCreateTeacherModal">取消</button>
			</view>
		  </view>
		</view>
		
		
		
		
		
		<!-- 删除教师的第一个确认弹窗 -->
		<view v-if="showFirstConfirmationModal1" class="modal-overlay">
		    <view class="modal-content">
		        <text>您确定要删除教师  <text style="color: red;">{{this.deleteTeacherName}}</text>  的全部信息吗？</text>
		        <view class="modal-buttons">
					<button class="modal-button confirm-button" @click="openSecondConfirmationModal1">确认</button>
					<button class="modal-button cancel-button" @click="closeFirstConfirmationModal1">取消</button>
		        </view>
		    </view>
		</view>
		
		<!-- 删除教师的第二个确认弹窗 -->
		<view v-if="showSecondConfirmationModal1" class="modal-overlay">
		    <view class="modal-content">
		        <text>删除教师信息属于  <text style="color: red;">敏感</text>  操作，<br>您确定要执行吗？<br><text style="color: red;">（该操作一旦执行便无法撤销）</text></text>
		        <view class="modal-buttons">
					<button class="modal-button confirm-button" @click="handleDeleteTeacher">确认</button>
					<button class="modal-button cancel-button" @click="closeSecondConfirmationModal1">取消</button>
		        </view>
		    </view>
		</view>
		
		
		
		
		
		
		<!-- 批量导入的第一个确认弹窗 -->
<!-- 		<view v-if="showFirstConfirmationModal" class="modal-overlay">
		    <view class="modal-content1">
		        <text>您确定要执行教师信息批量导入操作吗？</text>
		        <view class="modal-buttons">
					<button class="modal-button confirm-button" @click="openSecondConfirmationModal">确认</button>
					<button class="modal-button cancel-button" @click="closeFirstConfirmationModal">取消</button>
		        </view>
		    </view>
		</view> -->
		
		<!-- 批量导入的第二个确认弹窗 -->
<!-- 		<view v-if="showSecondConfirmationModal" class="modal-overlay">
		    <view class="modal-content">
		        <text>批量导入将<text style="color: red;">影响</text>现有的教师信息表单<br><text style="color: red;">（该操作一旦执行便无法撤销）</text></text>
		        <view class="modal-buttons">
					<button class="modal-button confirm-button" @click="handleBulkImport">确认</button>
					<button class="modal-button cancel-button" @click="closeSecondConfirmationModal">取消</button>
		        </view>
		    </view>
		</view> -->
			
			
			
			
			
		
		
		<!-- 教师列表展示 -->
		<view class="teacher-list-section">
		  <view class="teacher-item" v-for="teacher in teacherList" :key="teacher.teacherId">
		    <view class="teacher-card">
		      <text class="teacher-name">教师姓名：{{ teacher.name }}</text>
			  <!-- <button class="delete-button" @click="openFirstConfirmationModal1(teacher.teacherId,teacher.name)">删除教师️</button> -->
			  <text class="teacher-teacherId">教师账号：{{ teacher.teacherId }}</text>
			   <text class="teacher-email">教师邮箱：{{ teacher.email ||"无" }}</text>
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
				<view class="text"  style="color:#ff4d4f">教师管理</view>
			</view>
			<view class="footer-item" @click="goToProfile">
				<view class="icon">👤</view>
				<view class="text">系统管理</view>
			</view>
		</view>
	</view>
</template>






<script>
// import * as XLSX from 'xlsx';
import { config } from '../../../config'; // 导入 config.js 文件


export default {
    data() {
    	return {
			apiUrl: `http://${config.host}:${config.port}`, // 使用配置的host和port
			
			
			who:"",
			
			
			
			// 错误弹窗提示信息
			errorMessage: '',
			errorPopBackgroundColor: '#ff4d4f', // 错误弹窗背景颜色
			timeoutId: null,
			
			
			// 教师列表
			teacherList:[],
			
			
			
			// 新教师信息
			newTeacherName: "",
			newTeacherEmail:"",
			
			
			
			// 选择要删除的教师
			deleteTeacherId: "",
			deleteTeacherName:"",


			// 创建教师弹窗
			showCreateTeacherModal: false,
			
			
			
			// 批量导入确认弹窗
			// showFirstConfirmationModal: false,
			// showSecondConfirmationModal: false,
			
			// 删除教师确认弹窗
			showFirstConfirmationModal1: false,
			showSecondConfirmationModal1: false,
			
			
			

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
		
		
		
		this.loadTeacherList();
	},
	
	
	
	methods: {
		// 获取教师列表
		loadTeacherList(){
			uni.request({
			    url: `${this.apiUrl}/admin/queryAllTeacher`, 
			    method: 'GET',
			    success: (res) => {
					 // console.log(res);
			        if (res.data.code === '000') {
						this.teacherList = res.data.data;
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
		
		
		// 打开创建教师弹窗
		openCreateTeacherModal() {
			if(!this.who){
				// console.log('Debug: this.who is', this.who); 
				this.showError("请先登录！");
				return;
			}
		    this.showCreateTeacherModal = true;
		},
		
		// 关闭创建教师弹窗
		closeCreateTeacherModal() {
		    this.showCreateTeacherModal = false;
		    this.resetNewTeacherFields();
		},
		
		// 重置创建教师表单
		resetNewTeacherFields() {
		    this.newTeacherName="";
			this.newTeacherEmail="";
		},
		
		
		
		
		// 创建教师
		handleCreateTeacher(){
			if ( !this.newTeacherName || !this.newTeacherEmail) {
			    this.showError("教师姓名和邮箱均不能为空！");
			    return;
			}
			if (this.teacherList.some(teacher => teacher.teacherId == this.newTeacherId)) {
			    this.showError("该教师账号已存在！");
			    return;
			}
		    this.createTeacherRequest();
		},
		
		createTeacherRequest(){
			// 显示加载动画
			uni.showLoading({
				title: '正在创建教师...', // 加载动画的提示文字
				mask: true // 阻止点击背景时关闭加载提示
			});

			const teacherData = {
				name: this.newTeacherName ,   
				email: this.newTeacherEmail, 
			};

			uni.request({
				url: `${this.apiUrl}/admin/createTeacher`, // 替换为实际接口地址
				method: 'POST',
				data: teacherData, // 请求体数据
				header: {
					'Content-Type': 'application/json', // 请求头，内容类型为JSON
				},
				success: (res) => {
					if (res.data.code === '000') {
						this.showError("教师创建成功！", "#28a745");
						uni.showToast({
							title: '创建成功',  // 提示的文本
							icon: 'success',   // 提示图标
							duration: 1000     // 提示框的显示时长
						});
						this.loadTeacherList();
					} else {
						this.showError("教师创建失败！", "#ff4d4f");
					}
				},
				fail: (err) => {
					this.showError("网络错误，请稍后再试", "#ff4d4f");
				},
				complete: () => {
					uni.hideLoading();  // 请求完成后隐藏加载动画
					this.closeCreateTeacherModal(); // 关闭教师创建弹窗或相关操作
				}
			});
		},
		
		
		
		
		
		
		
		// 删除教师
		handleDeleteTeacher(){
			if (this.deleteTeacherId) {
				this.deleteTeacherRequest(this.deleteTeacherId);
			}
			if(true){
				this.showError("教师删除成功！", "#28a745");
				this.closeSecondConfirmationModal1();
			}
			else{
				this.showError("教师删除失败");
				this.closeSecondConfirmationModal1();
			}
		},
		deleteTeacherRequest(teacherId){
			// 这行代码只是模拟与服务器交互
			this.teacherList = this.teacherList.filter(teacher => teacher.teacherId !== teacherId);
			this.deleteTeacherId="";
			this.deleteTeacherName="";
		},
		
		
		
		
		
		// // 批量导入教师名单
		// handleBulkImport(){
		// 	this.chooseExcelFile();
		// 	this.closeSecondConfirmationModal();
		// },
		
		// chooseExcelFile(){
		// 	uni.chooseFile({
		// 	    count: 1, // 选择一个文件
		// 	    success: (res) => {
		// 			const file = res.tempFiles[0]; // 获取选择的第一个文件
		// 			if (!this.isValidExcel(file)) {
		// 				this.showError('请选择Excel文件!');
		// 				return;
		// 			}
		// 			this.uploadFile(file); // 上传文件
		// 	    },
		// 	    fail: (err) => {
		// 			// console.log('文件选择失败:', err);
		// 	    }
		// 	})
		// },
		
		// isValidExcel(file) {
		//     // 检查文件后缀是否为Excel格式
		//     const validExtensions = ['.xlsx', '.xls'];
		//     const fileExtension = file.name.slice(file.name.lastIndexOf('.')).toLowerCase();
		//     return validExtensions.includes(fileExtension);
		// },
		
		// uploadFile(file) {
		// 	uni.showLoading({
		// 	    title: '上传中...',
		// 	    mask: true
		// 	});
		// 	// 使用 uni.uploadFile 发送 POST 请求上传文件
		// 	uni.uploadFile({
		// 		url: 'http://localhost:8080/admin/importTeacherInfo',  
		// 		filePath: file.path,             
		// 		name: 'file',                    
				
		// 		success: (res) => {
		// 			console.log(res);
		// 			uni.hideLoading(); // 隐藏加载提示
		// 			if (res.data.code === '000') {
		// 				this.showError('文件导入成功！'); 
		// 			} 
		// 			else {
		// 				this.showError(res.data.info); 
		// 			}
		// 		},
		// 		fail: (error) => {
		// 			uni.hideLoading(); // 隐藏加载提示
		// 			this.showError('文件上传失败');
		// 		}
		// 	});
		// },

		
		
		
		
		
		// // “批量导入”确认弹窗
		// openFirstConfirmationModal() {
		// 	this.showFirstConfirmationModal = true;
		// },
		// openSecondConfirmationModal() {
		//     this.showFirstConfirmationModal = false;
		//     this.showSecondConfirmationModal = true;
		// },
		// closeFirstConfirmationModal() {
		//     this.showFirstConfirmationModal = false;
		// },
		// closeSecondConfirmationModal() {
		//     this.showSecondConfirmationModal = false;
		// },
		
		
		
		// “删除教师”确认弹窗
		openFirstConfirmationModal1(teacherId,Name) {
			this.showFirstConfirmationModal1 = true;
			this.deleteTeacherId = teacherId;
			this.deleteTeacherName=Name;
		},
		openSecondConfirmationModal1() {
		    this.showFirstConfirmationModal1 = false;
		    this.showSecondConfirmationModal1 = true;
		},
		closeFirstConfirmationModal1() {
		    this.showFirstConfirmationModal1 = false;
		},
		closeSecondConfirmationModal1() {
		    this.showSecondConfirmationModal1 = false;
		},
		
		
		
		
		// 底部点击导航栏按钮切换页面
		// goToHome() {
		// 	uni.redirectTo({
		// 		url: `/pages/index/admin/admin1?id=${this.who}`  // 添加 id 参数
		// 	});

		// },
		// goToTeachers() {
		// 	uni.pageScrollTo({
		// 		scrollTop: 0, // 滚动到页面顶部
		// 		duration: 500, // 滚动动画的持续时间（毫秒）
		// 	});
		// },
		// goToProfile() {
		// 	uni.redirectTo({
		// 		url: `/pages/index/admin/admin3?id=${this.who}`  // 将 id=this.who 添加到 URL 中
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
			uni.pageScrollTo({
				scrollTop: 0, // 滚动到页面顶部
				duration: 500, // 滚动动画的持续时间（毫秒）
			});
		},
		goToProfile() {
			if(this.who){
				uni.redirectTo({
					url: `/pages/index/admin/admin3?id=${this.who}`  // 添加 id 参数
				});
			}
			else{
				uni.reLaunch({
					url: "/pages/index/admin/admin3"
				});
			}
		},
		
		
		
		
		
		
		
		
		
		
	},
    
};
</script>


