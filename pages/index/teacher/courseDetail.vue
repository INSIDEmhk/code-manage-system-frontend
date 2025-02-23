<style scoped>
	.teacher-page {
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
	
	
	
	
	.create-job-button {
		background-color: #007bff;
		color: white;
		width: 200rpx;
		height: 60rpx;
		border: none;
		border-radius: 15rpx;
		font-size: 28rpx;
		text-align: center;
		line-height: 60rpx;
		margin-top:45rpx;
		margin-bottom:120rpx;
		cursor: pointer;
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
	
	
	.info-input2 {
	  width: 95%;            /* 宽度自适应父容器 */
	  height: 250rpx;          /* 初始高度 */
	  padding: 10rpx;          /* 内边距，避免文本紧贴边缘 */
	  border-radius: 10rpx;     /* 圆角边框 */
	  font-size: 28rpx;        /* 字体大小 */
	  line-height: 1.6;       /* 行高 */
	  overflow-y: auto;       /* 超过内容时自动显示纵向滚动条 */
	  border:1px solid gray;
	  margin-bottom: 60rpx;
	  text-align: left;
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
		
		
		
		
		<view class="course-detail">
			<!-- 显示课程信息 -->
			<view class="course-title">教学班级：{{ Class.name }}</view>
			<view class="course-info">班级人数：{{ Class.peopleCount }}人</view>
			<view class="course-info">课程名称：{{ this.courseName }}</view>
			<view class="course-info">课程开始日期：{{ formatDate(courseStartTime )}}</view>
			<view class="course-info">课程结束日期：{{ formatDate(courseEndTime) }}</view>
			<!-- <view class="course-info">任课教师：{{ classTeacherName }}</view> -->
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
				<view class="job-date">作业开始时间：{{ formatDate1(job.startTime )}} </view>
				<view class="job-date">作业截止时间：{{ formatDate1(job.endTime) }} </view>
			</view>
		</view>
		
		<!-- “新建作业”按钮 -->
		<button class="create-job-button" @click="handleCreateJob" >新建作业</button>
		
		
		
		<!-- 创建作业弹窗 -->
		<view v-if="showCreateJobModal" class="modal-overlay"  v-show="modalVisible">
		  <view class="modal-content1">
			  
		    <text class="info-label">作业标题：</text>
		    <input class="info-input1" v-model="jobTitle" placeholder="请输入作业标题" />
			
			<text class="info-label">作业内容：</text>
			<textarea class="info-input2" v-model="jobContent" placeholder="请输入作业内容" ></textarea>
			
		
		    <!-- 选择开始日期 -->
			<view class="flex-row">
				<text class="info-label">作业开始日期：</text>
				<picker mode="date"   :value="jobStartDate" start="2020-01-01" end="2030-12-31" @change="handleStartDateChange"  @cancel="handlePickerCancel">
					<button class="selectDate-button" @click="hideModalOverlay">点击选择开始日期</button>
				</picker>
			</view>
			<view class="info-input1">
				<span v-if="!jobStartDate" class="placeholder-text">请选择作业开始日期</span>
				<span v-else>{{ jobStartDate }}</span>
			</view>
			
			
			<!-- 选择开始时间 -->
			<view class="flex-row">
			  <text class="info-label">作业开始时间：</text>
			  <picker mode="time" :value="jobStartTime" start="00:00:00" end="23:59:59" @change="handleStartTimeChange" @cancel="handlePickerCancel">
			    <button class="selectDate-button" @click="hideModalOverlay">点击选择开始时间</button>
			  </picker>
			</view>
			<view class="info-input1">
			  <span v-if="!jobStartTime" class="placeholder-text">请选择作业开始时间</span>
			  <span v-else>{{ jobStartTime }}</span>
			</view>

		
		
		
		    <!-- 选择结束日期 -->
			<view class="flex-row">
				<text class="info-label">作业结束日期：</text>
				<picker mode="date" :value="jobEndDate" start="2020-01-01" end="2030-12-31" @change="handleEndDateChange"  @cancel="handlePickerCancel">
					<button class="selectDate-button" @click="hideModalOverlay">点击选择结束日期</button>
				</picker>
			</view>
			<view class="info-input1">
				<span v-if="!jobEndDate" class="placeholder-text">请选择作业结束日期</span>
				<span v-else>{{ jobEndDate }}</span>
			</view>
			
			<!-- 选择结束时间 -->
			<view class="flex-row">
			  <text class="info-label">作业结束时间：</text>
			  <picker mode="time" :value="jobEndTime" start="00:00:00" end="23:59:59" @change="handleEndTimeChange" @cancel="handlePickerCancel">
			    <button class="selectDate-button" @click="hideModalOverlay">点击选择结束时间</button>
			  </picker>
			</view>
			<view class="info-input1">
			  <span v-if="!jobEndTime" class="placeholder-text">请选择作业结束时间</span>
			  <span v-else>{{ jobEndTime }}</span>
			</view>
		
		
		
		
		    <view class="modal-buttons">
		      <button class="modal-button confirm-button1" @click="submitCreateJob">确认</button>
		      <button class="modal-button cancel-button"  @click="closeCreateJobModal">取消</button>
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
				
				
				// 错误弹窗提示信息
				errorMessage: '',
				errorPopBackgroundColor: '#ff4d4f', // 错误弹窗背景颜色
				timeoutId: null,
				
				
				
				// 课程详情数据
				Class:"",    
				classId:"",
				
				classTeacherName:"",
				courseName:"",
				
				courseStartTime:"",
				courseEndTime:"",
				
				
				// 作业数据
				jobList:"",
				ongoingJobList:[],
				completedJobList:[],
				
				
				
				showCreateJobModal: false,
				modalVisible: true, 
				
				
				// 新建作业信息
				jobTitle:"",
				jobContent:"",
				jobStartDate:"",
				jobEndDate:"",
				jobStartTime:"",
				jobEndTime:"",
				jobEntireStartTime:"",
				jobEntireEndTime:"",
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
			
			
			
			
			
			
			
			
			
			
			// 更新开始时间
			handleStartDateChange(event) {
				this.jobStartDate = event.detail.value; 
				this.modalVisible = true; // 选择完日期后显示 modal-overlay
			},
			
			    handleStartTimeChange(event) {
					this.jobStartTime = event.detail.value;  // 记录选择的时间
					this.modalVisible = true; // 选择完日期后显示 modal-overlay
			    },
			  
			// 更新结束时间
			handleEndDateChange(event) {
				this.jobEndDate = event.detail.value;  
				this.modalVisible = true; // 选择完日期后显示 modal-overlay
			},
			
				handleEndTimeChange(event) {
					this.jobEndTime = event.detail.value;  // 记录选择的时间
					this.modalVisible = true; // 选择完日期后显示 modal-overlay
				},
				
				
			
			// 选择取消时，恢复显示 modal-overlay
			handlePickerCancel() {
			    this.modalVisible = true; // 显示 modal-overlay
			},
			
			hideModalOverlay() {
			    this.modalVisible = false; // 点击选择按钮时隐藏 modal-overlay
			},
			
			
			
			
			
			// 创建学期弹窗		
			handleCreateJob() {
				if(!this.who){
					// console.log('Debug: this.who is', this.who); 
					this.showError("请先登录！");
					return;
				}
				this.showCreateJobModal = true;  
			},
			
			
			
			// 点击确认按钮提交创建学期表单
			submitCreateJob() {
				// 判断学期名，年月日是否为空
				if (!this.jobTitle || !this.jobContent || !this.jobStartDate || !this.jobEndDate || !this.jobStartTime || !this.jobEndTime) {
					this.showError("所有字段均不能为空！");
					return;
				}
				
				// 判断日期是否合法
				const startDateParts = this.jobStartDate.split('-'); 
				const endDateParts = this.jobEndDate.split('-'); 
				if (!this.isValidDate(startDateParts[0], startDateParts[1], startDateParts[2])) {
				    this.showError("开始日期无效！");
				    return;
				}
				if (!this.isValidDate(endDateParts[0], endDateParts[1], endDateParts[2])) {
				    this.showError("结束日期无效！");
				    return;
				}  
				// 判断开始日期是否小于结束日期
				const startDateObj = new Date(this.jobStartDate);
				const endDateObj = new Date(this.jobEndDate);
				if (startDateObj > endDateObj) {
				    this.showError("开始日期不能晚于结束日期！");
				    return;
				}
				
				
				
				// 将日期与时分秒合并
				this.jobEntireStartTime = `${this.jobStartDate}T${this.jobStartTime}:00+08:00`;
				this.jobEntireEndTime = `${this.jobEndDate}T${this.jobEndTime}:59+08:00`;
				
				console.log(this.jobEntireStartTime );
				console.log(this.jobEntireEndTime);
				
			
				// 向服务器发起创建学期的请求
				this.createJobRequest();
			},
			
			
			createJobRequest(){
				// 构建课程表单
				const jobData = {
					title: this.jobTitle,
					content: this.jobContent,
					classId:this.classId,
					courseId:this.Class.courseId,
					startTime:this.jobEntireStartTime,
					endTime:this.jobEntireEndTime
				};
				// 向服务器发送 POST 请求创建学期
				uni.showLoading({
				    title: '正在创建新作业...', // 加载动画的提示文字
				    mask: true // 阻止点击背景时关闭加载提示
				});
				uni.request({
					url: `${this.apiUrl}/teacher/createJob`, 
				    method: 'POST',
				    data: jobData, // 发送作业数据
				    success: (res) => {
						console.log(res);
						if (res.data.code === '000') {
							this.showError("作业创建成功！", "#28a745");
							this.loadClassDetail();
							
							this.closeCreateJobModal(); // 关闭创建作业弹窗
							
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
			
			
			resetCreateJobFields() {
			    this.jobTitle = '';
			    this.jobContent = '';
			    this.jobStartDate = '';
				this.jobEndDate = '';
				this.jobStartTime = '';
				this.jobEndTime = '';
				this.jobEntireStartTime = '';
				this.jobEntireEndTime = '';
			},
			
			
			isValidDate(year, month, day) {
			  const date = new Date(year, month - 1, day); // 月份减 1
			  return date.getFullYear() === parseInt(year) &&
			         date.getMonth() === (parseInt(month) - 1) &&
			         date.getDate() === parseInt(day);
			},
			
			
			
			// 点击取消按钮取消创建课程表单
			closeCreateJobModal() {
			    this.showCreateJobModal = false; 
			    this.resetCreateJobFields(); 
			},
			
			
			
			
			
			
			
			
			
			
			
			
			
			
			
			


			
			
			
			loadClassDetail(){
				uni.request({
					url: `${this.apiUrl}/teacher/queryClassByFactor`,
					method: 'POST',
					data:{
						classId:this.classId
					},
					success: (res) => {
						// console.log('课程班级信息：',res);
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
												this.courseName= res.data.data[0].name;
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
				  url: `/pages/index/teacher/jobDetail?classId=${this.classId}&jobId=${jobId}&id=${this.who}`  // 附加 jobId 和 id 参数
				});

			}
		}
	}
</script>


