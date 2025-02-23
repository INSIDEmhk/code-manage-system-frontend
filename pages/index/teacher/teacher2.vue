<style scoped>
	.teacher-page {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		width:637.5rpx;
		margin: auto; /* 自动居中 */
	}
	
	
	.header {
	  padding-top: 40rpx;
	  text-align: center;
	  font-size: 40rpx;
	  font-weight: bold;
	  margin-bottom: 20rpx;
	}
	
	.text-area {
	  width: 100%;
	  text-align: left;
	  padding-left: 20rpx;
	  font-size: 28rpx;
	  font-weight: bold;
	  margin-bottom: 20rpx;
	}
	
	.text{
		font-size:35rpx; 
	}
	.text1{
		font-size:30.5rpx; 
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
	
	
	
	
	/* “创建课程”按钮 */
	.create-course-button {
		background-color: #007bff;
		color: white;
		width: 170rpx;
		height: 60rpx;
		border: none;
		border-radius: 15rpx;
		font-size: 28rpx;
		text-align: center;
		line-height: 60rpx;
		margin-top: 5rpx;
		margin-bottom:120rpx;
		cursor: pointer;
	}
	
	
	
	
	
	.course-list {
		
	  width: 100%;
	  border: 1px solid gray;
	  border-radius: 20rpx;
	  padding: 10rpx;
	  margin-bottom: 120rpx;
	  min-height: 150rpx; /* 预留空间，防止空列表塌陷 */
	}
	
	.course-item {
		background-color: #f9f9f9;
		padding: 20rpx;
		margin: 10rpx 0;
		border-radius: 10rpx;
		box-shadow: 0 2rpx 6rpx rgba(0, 0, 0, 0.1);
		margin-bottom: 30rpx;
		height:140rpx;
		display: flex; /* 使用 flex 布局使得左侧矩形和右侧内容水平排列 */
	}
	
	.course-name {
	  font-size: 30rpx;
	  font-weight: bold;
	  margin-bottom: 25rpx;
	}
	
	.course-date {
	  font-size: 24rpx;
	  line-height: 35rpx;
	  color: #666;
	}
	
	/* 左侧的灰色矩形 */
	.course-left {
	  width: 180rpx; /* 设置矩形宽度 */
	  height: 135rpx; /* 设置矩形高度 */
	  background-color: #d3d3d3; /* 灰色背景 */
	  margin-right: 60rpx; /* 右侧间距 */
	  border-radius: 12rpx; /* 可选，设置圆角 */
	}
	
	/* 左侧的灰色矩形 */
	.course-left1 {
	  width: 150rpx; /* 设置矩形宽度 */
	  height: 135rpx; /* 设置矩形高度 */
	  background-color: #d3d3d3; /* 灰色背景 */
	  margin-right: 60rpx; /* 右侧间距 */
	  border-radius: 12rpx; /* 可选，设置圆角 */
	}
	
	/* 右侧的课程信息 */
	.course-right {
	  flex-grow: 1; /* 占据剩余空间 */
	}
	
	
	.course-info {
	  display: flex;
	  align-items: center;
	  margin-bottom: 20rpx; /* 添加底部间距，使按钮与课程信息产生间隔 */
	}
	
	
	
	
	/* 底部导航栏 */
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
	
	
	
	
	
	
	
	
	
	
	
	/* 确认页面 */
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
		animation: slideIn1 0.4s ease-out; /* 使用动画 */
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
	  /* background-color: #28a745; */
		background-color: #f44336;
		color: white;
	}
	
	.confirm-button1 {
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
	
	
	
	.info-input1 {
		width: 95%;
		padding: 10rpx;
		font-size: 28rpx;
		border-radius: 10rpx;
		/* margin:auto; */
		margin-bottom: 60rpx;
		margin-top:15rpx;
		border:1px solid gray;
		text-align: left;
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
	
	/* 让年月日三个输入框出现在同一行 */
	.flex-row {
		display: flex;
		justify-content: space-between; /* 或使用 space-around、center 等来控制间距 */
	}
	
	
	
	.placeholder-text {
	  font-size: 28rpx;
	  color: gray; 
	}
	
	
	.selectDate-button{
		  width: 240rpx;
		  height: 60rpx;
		  border-radius: 20rpx;
		  cursor: pointer;
		  font-size: 24rpx;
		  display: flex; 
		  align-items: center; 
		  justify-content: center;
		  text-align: center;  
		  border: none;  
		  background-color: lightseagreen;  
		  padding: 0;  
		  outline: none; 
		  color:white;
		  margin-top: -10rpx;  /* 稍微向上移动按钮 */
	}
	
	.selectDate-button:after{
		border: none; 
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
</style>






<template>
	<view class="teacher-page">
		<view class="error-pop" :class="{ active: this.errorMessage }" :style="{ backgroundColor: errorPopBackgroundColor }">{{ this.errorMessage }}</view>
		
		
		
		<view class="header">
		   <!-- <text class="text">课程列表</text> -->
		</view>
		
		<view class="text-area">
		    <text class="text">进行中的课程</text>
		</view>
		
		
		
		
		
		
		
		<view class="course-list">
		    <view class="course-item" v-for="course in ongoingCourses" :key="course.courseId" >
				<view class="course-left1"></view> <!-- 左侧的灰色矩形 -->
				<view class="course-right"> <!-- 右侧的课程信息 -->
					<view class="course-name">{{ course.name }}</view>
					<view class="course-date">{{formatDate(course.startTime) }} -<br> {{ formatDate(course.endTime) }}</view>
				</view>
				<button class="create-course-button" @click="handleCreateSemester(course.courseId)" >新建班级</button>
		    </view>
		</view>
		
		
		<!-- 创建班级弹窗 -->
		<view v-if="showCreateSemesterModal" class="modal-overlay"  v-show="modalVisible">
		  <view class="modal-content1">
		    <text class="info-label">班级名称：</text>
		    <input class="info-input1" v-model="className" placeholder="请输入班级名称" />
		
	
			<text class="info-label">班级人数：</text>
			<input class="info-input1" v-model="classPeopleCnt" placeholder="请输入班级人数" />
		
		
		
		    <view class="modal-buttons">
		      <button class="modal-button confirm-button1" @click="submitCreateSemester">确认</button>
		      <button class="modal-button cancel-button"  @click="closeCreateSemesterModal">取消</button>
		    </view>
		  </view>
		</view>
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		<view class="text-area">
		      <text class="text">已结束的课程</text>
		</view>
		
		<view class="course-list">
		      <view class="course-item" v-for="course in completedCourses" :key="course.courseId" >
				  <view class="course-left"></view> <!-- 左侧的灰色矩形 -->  
				  <view class="course-right"> <!-- 右侧的课程信息 -->
						<view class="course-name">{{ course.name }}</view>
						<view class="course-date">开始时间：{{ formatDate(course.startTime) }} <br> 结束时间：{{ formatDate(course.endTime) }}</view>
				  </view>
			  </view>
			  
		</view>
		
		<view class="text-area">
		      <text class="text">未开始的课程</text>
		</view>
		
		<view class="course-list">
		      <view class="course-item" v-for="course in upcomingCourses" :key="course.courseId" >
				  <view class="course-left"></view> <!-- 左侧的灰色矩形 -->  
				  <view class="course-right"> <!-- 右侧的课程信息 -->
						<view class="course-name">{{ course.name }}</view>
						<view class="course-date">开始时间：{{ formatDate(course.startTime) }} <br> 结束时间：{{ formatDate(course.endTime) }}</view>
				  </view>
				  
			  </view>
		</view>
		
		<!-- 底部导航栏（添加一段空白挤占空间，防止footer底部导航栏遮挡住最下面的作业） -->
		<view class="footer-blank"></view>
		<view class="footer">
			<view class="footer-item" @click="goToHome">
				<view class="icon">🏠</view>
				<view class="text">首页</view>
			</view>
			<view class="footer-item" @click="goToCourses">
				<view class="icon">📘</view>
				<view class="text" style="color:#ff4d4f">课程</view>
			</view>
			<view class="footer-item" @click="goToProfile">
				<view class="icon">👤</view>
				<view class="text">我的</view>
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
			
			
			
			// 错误弹窗提示信息
			errorMessage: '',
			errorPopBackgroundColor: '#ff4d4f', // 错误弹窗背景颜色
			timeoutId: null,
			
			
			
			upcomingCourses:"", // 未开始的课程
			ongoingCourses: "", // 进行中的课程
			completedCourses: "", // 已结束的课程
			
			
			
			showCreateSemesterModal: false,
			modalVisible: true, 
			
			selectCourse:"",
			activeSemester:"",
			className:"",
			classPeopleCnt:"",
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
		
		
		this.loadUpcomingCourses();
		this.loadOngoingCourses();
		this.loadCompletedCourses();
		
		
		this.loadActiveSemesterList();
	},
	
	
	
	methods: {
		// 格式化日期
		formatDate(date) {
			const d = new Date(date);
			return `${d.getFullYear()}年${d.getMonth() + 1}月${d.getDate()}日`;
		},
		
		
		
		
		
		// 创建学期弹窗
		handleCreateSemester(courseId) {
			if(!this.who){
				// console.log('Debug: this.who is', this.who); 
				this.showError("请先登录！");
				return;
			}
			this.selectCourse=courseId;
			this.showCreateSemesterModal = true;  
		},
		
		
		
		// 点击确认按钮提交创建学期表单
		submitCreateSemester() {
			// 判断学期名，年月日是否为空
			if (!this.className || !this.classPeopleCnt ) {
				this.showError("所有字段均不能为空！");
				return;
			}
		
			// 向服务器发起创建学期的请求
			this.createSemesterRequest();
		},
		
		
		createSemesterRequest(){
			// 构建学期数据对象
			const semesterData = {
				name: this.className,
				peopleCount:this.classPeopleCnt,
				teacherId:this.who,
				semesterId:this.activeSemester.toString(),
				courseId:this.selectCourse.toString(),
				
			};
			console.log(semesterData);
			// 向服务器发送 POST 请求创建学期
			uni.showLoading({
			    title: '正在创建新班级...', // 加载动画的提示文字
			    mask: true // 阻止点击背景时关闭加载提示
			});
			uni.request({
				url: `${this.apiUrl}/teacher/createClass`, 
			    method: 'POST',
			    data: semesterData, // 发送学期数据
			    success: (res) => {
					if (res.data.code === '000') {
						this.showError("创建成功！", "#28a745");
						this.closeCreateSemesterModal(); // 关闭创建学期弹窗
						uni.showToast({
						    title: '创建成功',  // 提示的文本
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
					
					// 隐藏加载动画
					uni.hideLoading();
				}
			});
		},
		
		
		resetCreateSemesterFields() {
		    this.className="";
			this.classPeopleCnt="";
			this.selectCourse="";
		},
		
		
		
		// 点击取消按钮取消创建学期表单
		closeCreateSemesterModal() {
		    this.showCreateSemesterModal = false; 
		    this.resetCreateSemesterFields(); 
		},
		
		
		
		
		
		
		
		
		// 获取启用学期的列表
		loadActiveSemesterList(){
			uni.request({
			    url: `${this.apiUrl}/admin/queryCurrentSemester`, 
			    method: 'GET',
			    success: (res) => {
					 console.log(res);
			        if (res.data.code === '000') {
						this.activeSemester = res.data.data.semesterId;
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
		
		
		
		
		
		
		loadUpcomingCourses(){
			// if(!this.who){
			// 	// console.log('Debug: this.who is', this.who); 
			// 	this.showError("网络错误，请稍后再试");
			// 	return;
			// }
			uni.request({
			    url: `${this.apiUrl}/admin/queryUpcomingCourse`, 
			    method: 'POST',
				data:{
					courseId: "",
					name: "",
					status: "",
					startTime: "",
					endTime: "",
					semesterId: ""
				},
			    success: (res) => {
					 // console.log(res);
			        if (res.data.code === '000') {
						this.upcomingCourses = res.data.data;
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
		
		loadOngoingCourses(){
			// if(!this.who){
			// 	// console.log('Debug: this.who is', this.who); 
			// 	this.showError("网络错误，请稍后再试");
			// 	return;
			// }
			uni.request({
			    url: `${this.apiUrl}/admin/queryOngoingCourse`, 
			    method: 'POST',
				data:{
					courseId: "",
					name: "",
					status: "",
					startTime: "",
					endTime: "",
					semesterId: ""
				},
			    success: (res) => {
					 // console.log(res);
			        if (res.data.code === '000') {
						this.ongoingCourses = res.data.data;
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
		
		loadCompletedCourses(){
			// if(!this.who){
			// 	// console.log('Debug: this.who is', this.who); 
			// 	this.showError("网络错误，请稍后再试");
			// 	return;
			// }
			uni.request({
			    url: `${this.apiUrl}/admin/queryCompletedCourse`, 
			    method: 'POST',
				data:{
					courseId: "",
					name: "",
					status: "",
					startTime: "",
					endTime: "",
					semesterId: ""
				},
			    success: (res) => {
					 // console.log(res);
			        if (res.data.code === '000') {
						this.completedCourses = res.data.data;
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
		

			
			
			
			
		// 底部导航栏按钮
		// goToHome() {
		// 	uni.redirectTo({
		// 		url: `/pages/index/teacher/teacher1?id=${this.who}`  // 添加 id 参数
		// 	});

		// },
		// goToCourses() {
		// 	uni.pageScrollTo({
		// 		scrollTop: 0, // 滚动到页面顶部
		// 		duration: 500, // 滚动动画的持续时间（毫秒）
		// 	});
		// },
		// goToProfile() {
		// 	uni.redirectTo({
		// 		url: `/pages/index/teacher/teacher3?id=${this.who}`  // 添加 id 参数
		// 	});

		// },
		
		goToHome() {
			if(this.who){
				uni.redirectTo({
					url: `/pages/index/teacher/teacher1?id=${this.who}`  // 添加 id 参数
				});
			}
			else{
				uni.reLaunch({
					url: "/pages/index/teacher/teacher1"
				});
			}
		
		},
		goToCourses() {
			uni.pageScrollTo({
				scrollTop: 0, // 滚动到页面顶部
				duration: 500, // 滚动动画的持续时间（毫秒）
			});
		},
		goToProfile() {
			if(this.who){
				uni.redirectTo({
					url: `/pages/index/teacher/teacher3?id=${this.who}`  // 添加 id 参数
				});
			}
			else{
				uni.reLaunch({
					url: "/pages/index/teacher/teacher3"
				});
			}
		},
		
		
		
		
		
		
		
		
		
	},
};
</script>


