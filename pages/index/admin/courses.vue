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
	
	
	
	
	/* “创建课程”按钮 */
	.create-course-button {
		background-color: #007bff;
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
	
/* 	.create-course-button:active{
		background-color: #0056b3; 
		border: none; 
	} */
	
	
	
	
	
	
	
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
	<view class="admin-page">
		<view class="error-pop" :class="{ active: this.errorMessage }" :style="{ backgroundColor: errorPopBackgroundColor }">{{ this.errorMessage }}</view>
		<view class="header">
		   <!-- <text class="text">课程列表</text> -->
		</view>
		
		<view class="text-area">
		    <text class="text">进行中的课程</text>
		</view>
		
		<view class="course-list">
		    <view class="course-item" v-for="course in ongoingCourses" :key="course.courseId" >
				<view class="course-left"></view> <!-- 左侧的灰色矩形 -->
				<view class="course-right"> <!-- 右侧的课程信息 -->
					<view class="course-name">{{ course.name }}</view>
					<view class="course-date">开始时间：{{ formatDate(course.startTime) }} <br> 结束时间：{{ formatDate(course.endTime) }}</view>
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
		
		
		<!-- “新建课程”按钮 -->
		<button class="create-course-button" @click="handleCreateCourse" >新建课程</button>
		
		
		
		
		
		<!-- 创建课程弹窗 -->
		<view v-if="showCreateCourseModal" class="modal-overlay"  v-show="modalVisible">
		  <view class="modal-content1">
		    <text class="info-label">课程名称：</text>
		    <input class="info-input1" v-model="courseName" placeholder="请输入课程名称" />
			
		
		    <!-- 选择开始时间 -->
			<view class="flex-row">
				<text class="info-label">课程开始时间：</text>
				<picker mode="date"   :value="startDate" start="2020-01-01" end="2030-12-31" @change="handleStartDateChange"  @cancel="handlePickerCancel">
					<button class="selectDate-button" @click="hideModalOverlay">点击选择开始时间</button>
				</picker>
			</view>
			<view class="info-input1">
				<span v-if="!startDate" class="placeholder-text">请选择课程开始时间</span>
				<span v-else>{{ startDate }}</span>
			</view>
		
		
		
		    <!-- 选择结束时间 -->
			<view class="flex-row">
				<text class="info-label">课程结束时间：</text>
				<picker mode="date" :value="endDate" start="2020-01-01" end="2030-12-31" @change="handleEndDateChange"  @cancel="handlePickerCancel">
					<button class="selectDate-button" @click="hideModalOverlay">点击选择结束时间</button>
				</picker>
			</view>
			<view class="info-input1"><!-- {{ endDate || '请选择学期结束时间'}} -->
				<span v-if="!endDate" class="placeholder-text">请选择课程结束时间</span>
				<span v-else>{{ endDate }}</span>
			</view>
		
		
		
		
		    <view class="modal-buttons">
		      <button class="modal-button confirm-button1" @click="submitCreateCourse">确认</button>
		      <button class="modal-button cancel-button"  @click="closeCreateCourseModal">取消</button>
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
			
			
			
			upcomingCourses:"", // 未开始的课程
			ongoingCourses: "", // 进行中的课程
			completedCourses: "", // 已结束的课程
			
			
			// 创建课程操作:输入创建学期信息
			courseName: '',
			startDate: '', 
			endDate: '', 
			activeSemesterId:'',
			
			
			showCreateCourseModal: false,  
			modalVisible: true, 
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
		
		this.activeSemesterId=query.activeSemesterId;
		console.log(this.activeSemesterId);  // 输出传递的 semesterId
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
		
		
		// 更新开始时间
		handleStartDateChange(event) {
			this.startDate = event.detail.value; 
			this.modalVisible = true; // 选择完日期后显示 modal-overlay
		},
		  
		// 更新结束时间
		handleEndDateChange(event) {
			this.endDate = event.detail.value;  
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
		handleCreateCourse() {
			if(!this.who){
				// console.log('Debug: this.who is', this.who); 
				this.showError("请先登录！");
				return;
			}
			this.showCreateCourseModal = true;  
		},
		
		
		
		// 点击确认按钮提交创建学期表单
		submitCreateCourse() {
			// 判断学期名，年月日是否为空
			if (!this.courseName || !this.startDate || !this.endDate) {
				this.showError("所有字段均不能为空！");
				return;
			}
			
			// 判断日期是否合法
			const startDateParts = this.startDate.split('-'); 
			const endDateParts = this.endDate.split('-'); 
			if (!this.isValidDate(startDateParts[0], startDateParts[1], startDateParts[2])) {
			    this.showError("开始日期无效！");
			    return;
			}
			if (!this.isValidDate(endDateParts[0], endDateParts[1], endDateParts[2])) {
			    this.showError("结束日期无效！");
			    return;
			}  
			// 判断开始日期是否小于结束日期
			const startDateObj = new Date(this.startDate);
			const endDateObj = new Date(this.endDate);
			if (startDateObj > endDateObj) {
			    this.showError("开始日期不能晚于结束日期！");
			    return;
			}
		
			// 向服务器发起创建学期的请求
			this.createCourseRequest();
		},
		
		
		createCourseRequest(){
			// 构建课程表单
			const courseData = {
				name: this.courseName,
				startTime: this.startDate,
				endTime: this.endDate,
				semesterId:this.activeSemesterId,
			};
			// 向服务器发送 POST 请求创建学期
			uni.showLoading({
			    title: '正在创建新课程...', // 加载动画的提示文字
			    mask: true // 阻止点击背景时关闭加载提示
			});
			uni.request({
				url: `${this.apiUrl}/admin/createCourse`, 
			    method: 'POST',
			    data: courseData, // 发送课程数据
			    success: (res) => {
					if (res.data.code === '000') {
						this.showError("课程创建成功！", "#28a745");
						this.loadUpcomingCourses();
						this.loadOngoingCourses();
						this.loadCompletedCourses();
						
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
					this.closeCreateCourseModal(); // 关闭创建学期弹窗
					// 隐藏加载动画
					uni.hideLoading();
				}
			});
		},
		
		
		resetCreateCourseFields() {
		    this.courseName = '';
		    this.startDate = '';
		    this.endDate = '';
			// this.semesterId='';
		},
		
		
		isValidDate(year, month, day) {
		  const date = new Date(year, month - 1, day); // 月份减 1
		  return date.getFullYear() === parseInt(year) &&
		         date.getMonth() === (parseInt(month) - 1) &&
		         date.getDate() === parseInt(day);
		},
		
		
		
		// 点击取消按钮取消创建课程表单
		closeCreateCourseModal() {
		    this.showCreateCourseModal = false; 
		    this.resetCreateCourseFields(); 
		},
		
		
		
		
		
		
		
		
		
		
		
		
		loadUpcomingCourses(){
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
			
			

	},
};
</script>


