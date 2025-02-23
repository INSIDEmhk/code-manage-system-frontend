<style scoped>
	.student-page {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		width:637.5rpx;
		margin: auto; /* 自动居中 */
	}
	.text-area {
	  width: 100%;
	  text-align: left;
	  padding-left: 20rpx;
	  font-size: 28rpx;
	  /* font-weight: bold; */
	  margin-bottom: 10rpx;
	}
	.text{
		font-size:33rpx; 
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
	
	
	
	/* 课程详细信息样式 */
		.course-detail {
			width: 100%;
			padding: 20rpx;
			margin-bottom: 40rpx;
			margin-top:40rpx;
		}
	
		.course-title {
			font-size: 36rpx;
			font-weight: bold;
			margin-bottom: 20rpx;
		}
	
		.course-info {
			font-size: 28rpx;
			color: #666;
			margin-bottom: 15rpx;
		}
		
		
		
	
	/* 作业列表样式 */
		.job-list {
			width: 100%;
			border: 1px solid gray;
			border-radius: 20rpx;
			padding: 10rpx;
			margin-top: 10rpx;
			min-height:160rpx;
			margin-bottom:80rpx;
		}
	
		.job-item {
			background-color: #f9f9f9;
			padding: 15rpx;
			padding-top: 30rpx;
			margin-bottom: 20rpx;
			border-radius: 10rpx;
			box-shadow: 0 2rpx 6rpx rgba(0, 0, 0, 0.1);
			height:120rpx;
		}
		.job-title {
		  font-size: 30rpx;
		  font-weight: bold;
		  margin-bottom: 25rpx;
		}
		
		.job-date {
		  font-size: 24rpx;
		  color: #666;
		  line-height:36rpx;
		}
	
	

</style>



<template>
	<view class="student-page">
		<view class="error-pop" :class="{ active: this.errorMessage }" :style="{ backgroundColor: errorPopBackgroundColor }">{{ this.errorMessage }}</view>
		
		
		
		
		<view class="course-detail">
			<!-- 显示课程信息 -->
			<view class="course-title">教学班级：{{ Class.name }}</view>
			<view class="course-info">班级人数：{{ Class.peopleCount }}人</view>
			<view class="course-info">课程开始日期：{{ formatDate(courseStartTime )}}</view>
			<view class="course-info">课程结束日期：{{ formatDate(courseEndTime) }}</view>
			<view class="course-info">任课教师：{{ classTeacherName }}</view>
		</view>
		
		<!-- 进行中的作业 -->
		<view class="text-area">
		    <text class="text">进行中的作业</text>
		</view>
		<view class="job-list" >
			<view class="job-item" v-for="(job, index) in ongoingJobList" :key="index" @click="goToJobDetail(job.jobId)">
				<view class="job-title">{{ job.title }}</view>
				<view class="job-date">作业开始时间：{{ formatDate1(job.startTime )}} </view>
				<view class="job-date">作业截止时间：{{ formatDate1(job.endTime )}} </view>
			</view>
		</view>
		
		<!-- 已截止的作业 -->
		<view class="text-area">
		    <text class="text">已截止的作业</text>
		</view>
		<view class="job-list" >
			<view class="job-item" v-for="(job, index) in completedJobList" :key="index" @click="goToJobDetail(job.jobId)">
				<view class="job-title">{{ job.title }}</view>
				<view class="job-date">截止时间：{{ formatDate1(job.endTime) }} </view>
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
				
				
				
				// 课程详情数据
				Class:"",    
				classId:"",
				
				classTeacherName:"",
				
				courseStartTime:"",
				courseEndTime:"",
				
				
				// 作业数据
				jobList:"",
				ongoingJobList:[],
				completedJobList:[],
			}
		},
		
		onLoad(query) {
			console.log(query.id);
			this.who=query.id;
			
			
			// 根据 courseId 获取该课程的详细信息
			// console.log(query.classId);
			this.classId=query.classId;
			
			if(!this.who){
				// console.log('Debug: this.who is', this.who); 
				this.showError("请先登录！");
				uni.reLaunch({
					// (url后期需要修改！！！)
				    url: "/pages/index/login"
				});
				return;
			}
			
			// 获取班级信息
			this.loadClassDetail();
		},
		
		
		
		methods: {
			// 格式化日期
			formatDate(date) {
				const d = new Date(date);
				return `${d.getFullYear()}年${d.getMonth() + 1}月${d.getDate()}日`;
			},
			
			
			// 格式化年月日时分秒
			formatDate1(date) {
				const date1 = new Date(date);  // 将传入的日期转化为 Date 对象
				const year = date1.getFullYear(); // 获取年份
				const month = date1.getMonth() + 1; // 获取月份，+1 因为月份是从 0 开始的
				const day = date1.getDate(); // 获取日期
				const hours = date1.getHours(); // 获取小时
				const minutes = date1.getMinutes(); // 获取分钟
				const seconds = date1.getSeconds(); // 获取秒钟

				// 返回格式化后的日期字符串，带 "年", "月", "日", "时", "分", "秒"
				return `${year}年${month}月${day}日 ${hours}时${minutes}分${seconds}秒`;
			},


			
			
			
			loadClassDetail(){
				// if(!this.who){
				// 	// console.log('Debug: this.who is', this.who); 
				// 	this.showError("网络错误，请稍后再试");
				// 	return;
				// }
				uni.request({
					url: `${this.apiUrl}/teacher/queryClassByFactor`,
					method: 'POST',
					data:{
						classId:this.classId
					},
					success: (res) => {
						if (res.data.code === '000') {
							this.Class = res.data.data[0];
						
							
									// 查询课程开始日期和结束日期
									uni.request({
										url: `${this.apiUrl}/admin/queryCourse`,
										method: 'POST',
										data:{
											courseId:this.Class.courseId
										},
										success: (res) => {
											// console.log(res);
											if (res.data.code === '000') {
												this.courseStartTime = res.data.data[0].startTime;
												this.courseEndTime = res.data.data[0].endTime;
											} 
											else {
												this.showError(res.data.info); // 显示错误信息
											}
										},
										fail: () => {
											this.showError("网络错误，请稍后再试");
										}
									});
									
									
									// 查询教师姓名
									uni.request({
										url: `${this.apiUrl}/api/queryTeacherById?id=${this.Class.teacherId}`,
										method: 'GET',
										success: (res) => {
											// console.log(res);
											if (res.data.code === '000') {
												this.classTeacherName = res.data.data.name;
											} 
											else {
												this.showError(res.data.info); // 显示错误信息
											}
										},
										fail: () => {
											this.showError("网络错误，请稍后再试");
										}
									});
									
									
									
									// 获取作业列表
										const currentDate = new Date();  // 获取当前日期和时间
										uni.request({
											url: `${this.apiUrl}/teacher/queryJobByFactor`,
											method: 'POST',
											data:{
												classId:this.Class.classId
											},
											success: (res) => {
												// console.log(res);
												if (res.data.code === '000') {
													this.jobList=res.data.data;
													this.ongoingJobList= this.jobList.filter(job => new Date(job.endTime) > currentDate);
													this.completedJobList= this.jobList.filter(job => new Date(job.endTime) <= currentDate);
												} 
												else {
													this.showError(res.data.info); // 显示错误信息
												}
											},
											fail: () => {
												this.showError("网络错误，请稍后再试");
											}
										});
								
							
							
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
			
			// 点击作业跳转到 jobDetail.vue
			goToJobDetail(jobId) {
				uni.navigateTo({
				  url: `/pages/index/student/jobDetail?jobId=${jobId}&id=${this.who}`  // 附加 jobId 和 id 参数
				});

			}
		}
	}
</script>


