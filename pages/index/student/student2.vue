<style scoped>
	.student-page {
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
	
	/* 右侧的课程信息 */
	.course-right {
	  flex-grow: 1; /* 占据剩余空间 */
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
</style>






<template>
	<view class="student-page">
		<view class="error-pop" :class="{ active: this.errorMessage }" :style="{ backgroundColor: errorPopBackgroundColor }">{{ this.errorMessage }}</view>
		
		
		
		<view class="header">
		   <!-- <text class="text">课程列表</text> -->
		</view>
		
		<view class="text-area">
		    <text class="text">进行中的课程</text>
		</view>
		
		<view class="course-list">
		    <view class="course-item" v-for="course in ongoingCourses" :key="course.courseId">
				<view class="course-left"></view> <!-- 左侧的灰色矩形 -->
				<view class="course-right"> <!-- 右侧的课程信息 -->
					<view class="course-name">{{ course.name }}</view>
					<view class="course-date">开始时间：{{formatDate(course.startTime) }} <br> 结束时间：{{ formatDate(course.endTime) }}</view>
				</view>
		    </view>
		</view>
		
		<view class="text-area">
		      <text class="text">已结束的课程</text>
		</view>
		
		<view class="course-list">
		      <view class="course-item" v-for="course in completedCourses" :key="course.courseId">
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
		      <view class="course-item" v-for="course in upcomingCourses" :key="course.courseId">
		      <view class="course-left"></view> <!-- 左侧的灰色矩形 -->  
			  <view class="course-right"> <!-- 右侧的课程信息 -->
					<view class="course-name">{{ course.name }}</view>
					<view class="course-date">开始时间：{{ formatDate(course.startTime) }} <br> 结束时间：{{ formatDate(course.endTime) }}</view>
		      </view>
			  </view>
		</view>
		
		<!-- 底部导航栏 -->
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
			
			
			// activeSemester:"",
			
			upcomingCourses:"", // 未开始的课程
			ongoingCourses: "", // 进行中的课程
			completedCourses: "", // 已结束的课程
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
		
		
		// this.loadActiveSemesterList();
		
		
		this.loadUpcomingCourses();
		this.loadOngoingCourses();
		this.loadCompletedCourses();
	},
	
	
	
	methods: {
		// 格式化日期
		formatDate(date) {
			const d = new Date(date);
			return `${d.getFullYear()}年${d.getMonth() + 1}月${d.getDate()}日`;
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
		
		
		
		
		// 获取启用学期的列表
		// loadActiveSemesterList(){
		// 	if(!this.who){
		// 		// console.log('Debug: this.who is', this.who); 
		// 		this.showError("网络错误，请稍后再试");
		// 		return;
		// 	}
		// 	uni.request({
		// 	    url: 'http://localhost:8080/admin/queryCurrentSemester', 
		// 	    method: 'GET',
		// 	    success: (res) => {
		// 			 // console.log(res);
		// 	        if (res.data.code === '000') {
		// 				this.activeSemester = res.data.data;
		// 	        } 
		// 			else {
		// 				this.showError(res.data.info); // 显示错误信息
		// 	        }
		// 	    },
		// 	    fail: () => {
		// 			this.showError("网络错误，请稍后再试");
		// 	    }
		// 	});
		// },
		
		
		// goToCourseDetail(courseId) {
		// 	uni.navigateTo({
		// 		url: `/pages/index/student/courseDetail?courseId=${courseId}&id=${this.who}`  // 添加 courseId 和 id 参数
		// 	});
		// },
		
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
			uni.pageScrollTo({
				scrollTop: 0, // 滚动到页面顶部
				duration: 500, // 滚动动画的持续时间（毫秒）
			});
		},
		goToProfile() {
			if(this.who){
				uni.redirectTo({
					url: `/pages/index/student/student3?id=${this.who}`  // 添加 id 参数
				});
			}
			else{
				uni.reLaunch({
					url: "/pages/index/student/student3"
				});
			}

		},
		
		
		
		
	},
};
</script>


