<style scoped>
	.student-page {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		width:637.5rpx;
		margin: auto; 
	}
	
	
	
	.header{
		padding-top:40rpx;
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: center;
		width: 100%; 
		margin-bottom:-15rpx;
	}
	

	
	.text-area{
		width: 100%; 
		text-align: left; 
		padding-left: 20rpx; 
		font-size: 28rpx; 
		font-weight: bold; 
		margin-bottom: 0rpx; 
		display:flex;
		flex-direction:row;
	}
	
	.text{
		font-size:35rpx; 
		flex-grow: 1; /* 占据剩余空间，让行内剩余元素紧靠右侧 */
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
	
	
	
	.ai-button {
		background-color: #007bff;
		color: white;
		width: 200rpx;
		height: 60rpx;
		border: none;
		border-radius: 15rpx;
		font-size: 28rpx;
		text-align: center;
		line-height: 60rpx;
		margin-top: 0rpx;
		margin-bottom:0rpx;
		cursor: pointer;
		margin-right: 0;
		transform: translate(-5rpx, -38rpx);
	}
	
	.ai-button1 {
		background-color: #007bff;
		color: white;
		width: 200rpx;
		height: 60rpx;
		border: none;
		border-radius: 15rpx;
		font-size: 28rpx;
		text-align: center;
		line-height: 60rpx;
		margin-top: 0rpx;
		margin-bottom:0rpx;
		cursor: pointer;
	}
	
	

	
	/* “进行中的课程”展示区域 */
	.enabled_courseList-section{
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		width:100%;
		height:360rpx;
		margin-bottom:40rpx;
		white-space: nowrap; 
		margin-top:20rpx;
	}

	.course-scroll{
		display: flex;
		flex-direction: row;
		overflow-x: auto; 
		white-space: nowrap; 
		padding: 10rpx; 
		width: 100%;
		height: 360rpx; 
		border: 1px solid gray;
	}
	
	.course-card{
		display: inline-block; /* 防止卡片被挤压，不加上会导致只显示一个课程卡片 */
		align-items: center;
		justify-content: center;
		width: 220rpx;
		height: 300rpx;
		background-color: #F0F0F0;
		border-radius: 15rpx;
		margin-right: 20rpx; 
		box-shadow: 0 2rpx 6rpx rgba(0, 0, 0, 0.1); 
		padding: 25rpx;
		margin-left:20rpx;
		text-align: center;
		/* animation: slideIn1 0.4s ease-out;  */
	}
	
	.course-image{
		width: 180rpx;
		height: 160rpx;
		background-color: #dcdcdc; 
		border-radius: 10rpx;
		margin-bottom: 10rpx;
		
	}
	
	.course-name{
		font-size: 24rpx;
		font-weight: bold;
		color: #333333;
		margin-bottom: 5rpx;
	}
	
	.course-date{
		font-size: 20rpx;
		color: #666666;
	}
	
	
	
	
	

	/* “待提交的作业”展示区域 */
	.unfinished_studentJobList-section{
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		border: 1px solid gray;
		border-radius: 20rpx;
		width:100%;
		margin-top:20rpx;
		height:auto;
		min-height:200rpx;
		margin-bottom:20rpx;
	}
	
	.job-card {
	  width: 90%; 
	  background-color: #f9f9f9;
	  border-radius: 15rpx;
	  padding: 20rpx;
	  margin-bottom: 20rpx;
	  box-shadow: 0 2rpx 6rpx rgba(0, 0, 0, 0.1); 
	  /* animation: slideIn 0.4s ease-out;  */
	}
	
	.job-title {
	  font-size: 30rpx;
	  font-weight: bold;
	  margin-bottom: 10rpx;
	}
	
	.job-content {
	  font-size: 26rpx;
	  color: #666666;
	  margin-bottom: 10rpx;
	}
	
	.job-date {
	  font-size: 24rpx;
	  color: #999999;
	}






	/* “筛选”按钮 */
	.select-button{
		width:180rpx;
		height:50rpx;
		cursor: pointer; 
		/* (url后期需要修改！！！) */
	    background-image: url('/static/select_button.png'); 
	    background-size: cover;
	    background-position: center; 
		border:1px solid transparent;
		outline: none; 
	}
	
	.select-button:after{
		border: none; 
	}
	
	
	
	
	
	
	/* 侧面弹窗 */
	.sidebar-overlay {
	    position: fixed;
	    top: 0;
	    left: 0;
	    width: 100%;
	    height: 100%;
	    background-color: rgba(0, 0, 0, 0.3);
	    z-index: 1000;
	    display: none; /* 默认隐藏 */
	    opacity: 0;
	    transition: opacity 0.3s ease;
		z-index: 2000; /* 提高遮罩层的层级 */
	}
	
	.sidebar-overlay.show {
	    display: block;
	    opacity: 1;
	}
	
	.sidebar {
	    position: fixed;
	    top: 0;
	    right: -80%; 
	    width: 67%; 
	    height: 100%;
	    background-color: #ffffff;
	    z-index: 1001;
	    box-shadow: -4px 0 8px rgba(0, 0, 0, 0.2);
	    transition: right 0.3s ease;
		border-radius:30rpx;
		z-index: 3000; /* 侧边弹窗 z-index 设置较高 */
	}
	
	.sidebar.show {
	    right: 0;
	}
	
	.sidebar-header {
	    padding: 20px;
	    font-size: 18px;
	    font-weight: bold;
	    color: #333333;
	    border-bottom: 1px solid #dddddd;
	}
	
	.sidebar-content {
	    padding: 20px;
	    font-size: 16px;
	    color: #555555;
	}
	
	.sidebar-footer {
		display: flex;
		justify-content: space-around;
		padding: 20rpx;
		border-top: 1px solid #ddd;
		background-color: #f9f9f9;
	}
	
	.reset-button,
	.confirm-button {
		width: 200rpx;
		height: 60rpx;
		border: none;
		border-radius: 10rpx;
		font-size: 28rpx;
		cursor: pointer;
		text-align: center;
		line-height: 60rpx;
	}
	
	.reset-button {
		background-color: #f44336; /* 红色背景 */
		color: white;
	}
	
	.confirm-button {
		background-color: #4caf50; /* 绿色背景 */
		color: white;
	}
	
	
	
	
	
	
	/* 课程按钮样式 */
	.course-item {
	  display: inline-block;
	  padding: 10rpx 20rpx;
	  margin: 10rpx;
	  border: 1px solid #ccc;
	  border-radius: 30rpx; /* 圆角样式 */
	  background-color: #f5f5f5;
	  color: #333;
	  font-size: 28rpx;
	  text-align: center;
	  cursor: pointer;
	  transition: all 0.3s ease;
	}
	
	.course-item.selected {
	  background-color: #007bff; /* 选中后的背景色 */
	  color: white; /* 选中后的文字颜色 */
	  border-color: #007bff;
	}
	
	
	
	/* 动画：滑入 */
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
	@keyframes slideIn1 {
	  0% {
	    transform: translateX(-30rpx);
	    opacity: 0;
	  }
	  100% {
	    transform: translateX(0);
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
	  bottom: 0rpx;
	  left: 0;
	  width: 100%;
	  height: 100rpx;
	  background-color: #f9f9f9;
	  border-top: 1px solid #e0e0e0;
	  box-shadow: 0 -2rpx 4rpx rgba(0, 0, 0, 0.1);
	  z-index: 1000;
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
	
	.cancel-button {
		background-color: black;
		color: white;
		width: 200rpx;
/* 		margin-right:10rpx;
		margin-bottom:100rpx; */
	}
	
	.info-label1 {
		font-size: 34rpx;
		margin-bottom: 40rpx;
		margin-top:-50rpx;
		display: flex; 
		justify-content: center ;
		color:red;
	}

	
	.info-label {
		font-size: 28rpx;
		margin-bottom: 10rpx;
		display: flex; 
		justify-content: flex-start; /* 左对齐 */
	}
	
	
	.info-input3 {
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
	
	
	.info-input2 {
	  width: 95%;            /* 宽度自适应父容器 */
	  height: 100rpx;          /* 初始高度 */
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
	<view class="student-page">
		<view class="error-pop" :class="{ active: this.errorMessage }" :style="{ backgroundColor: errorPopBackgroundColor }">{{ this.errorMessage }}</view>
		
		
		
		
		<!-- 侧面弹窗 -->
		<view class="sidebar-overlay" :class="{ 'show': isSidebarVisible }" @click="closeSidebar"></view>
		<view class="sidebar" :class="{ 'show': isSidebarVisible }">
		    <view class="sidebar-header">
		        <text>筛选课程作业</text>
		    </view>
		    <view class="sidebar-content">
				    <view 
					   class="course-item" 
					   v-for="course in enabled_courseList" 
					   :key="course.courseId" 
					   :class="{ selected: selected_enabled_courseList_temp.some(item => item.courseId === course.courseId) }"
					   @click="toggleCourseSelection(course)"
				    >
		            {{ course.name }}
		       </view>   
		    </view>
		    <view class="sidebar-footer">
				<button class="confirm-button" @click="confirmSelection">保存</button>
		        <button class="reset-button" @click="resetSelection">重置</button>
		    </view>
		</view>
		
		
		
		<view class="header">
		    <text class="text">你好！ <text style="font-weight: bold;"  v-if="studentInf && studentInf[0] && !studentInf[1]" >{{ this.studentInf[0].name }}</text> 同学</text>
		</view>
		
		
		
		
		
		
		
		
		
		<button class="ai-button" @click="openAskAiModal" >AI解答</button>
		
		
		<!-- ai弹窗 -->
		<view v-if="showAskAiModal" class="modal-overlay"  v-show="modalVisible">
		  <view class="modal-content1">

			  
			  
		    <text class="info-label">当前学生端已接入kimi智能助手^_^</text>
		    <textarea class="info-input2" v-model="question" placeholder="请输入要询问的问题" />
			
			<text class="info-label1" v-if="asking">kimi正在思考中...</text>
			

			
			<text class="info-label">ai解答：</text>
			<textarea class="info-input3" v-model="answer" placeholder="kimi助手将回答您的问题" :disabled="true"/>
		
			
			<view class="modal-buttons">
				<button class="ai-button1"   @click="askAiRequest">发送问题</button>
				<button class="modal-button cancel-button"   @click="closeAskAiModal">退出问答</button>	
				
			</view>

		  </view>
		</view>
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		<view class="text-area">
			<text class="text">进行中的课程班级</text>
		</view>
		
		<view class="enabled_courseList-section">
			<scroll-view class="course-scroll" scroll-x>
			    <view class="course-card"  v-for="course in enabled_courseList"  :key="course.courseId"   @click="goToCourseDetail(course.classId)">
			        <image class="course-image" />
			        <view class="course-name">{{ course.name }}</view>
					<text class="course-date">班级编号：{{course.classId}} </text>
					<br>
					<text class="course-date">课程编号：{{ course.courseId }}&nbsp;&nbsp;&nbsp;&nbsp;</text>
			    </view>
			</scroll-view>
		</view>
		
		
		
		
		<view class="text-area">
			<text class="text">进行中的作业</text>
			<button @click="openSidebar" class="select-button"></button>
		</view>
		<view class="unfinished_studentJobList-section">
			<view class="job-card" v-for="job in selected_unfinished_studentJobList" :key="job.jobId" @click="goToJobDetail(job.jobId)">
				<view class="job-title">{{ job.title }}</view>
				<view class="job-content">{{ job.content }}</view>
				<view class="job-date">{{ formatDate(job.startTime) }} - {{  formatDate(job.endTime) }}</view>
			  </view>
		</view>
		
		
		
		<!-- 底部导航栏（添加一段空白挤占空间，防止footer底部导航栏遮挡住最下面的作业） -->
		<view class="footer-blank"></view>
		<view class="footer">
			<view class="footer-item" @click="goToHome">
				<view class="icon">🏠</view>
				<view class="text" style="color:#ff4d4f">首页</view>
			</view>
			<view class="footer-item" @click="goToCourses">
				<view class="icon">📘</view>
				<view class="text">课程</view>
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
				pyapiUrl: `http://${config.host}:${config.pyport}`, // 使用配置的host和port
				
				who:"",
				
				
				
				isAiPopupVisible: false, // 控制 AI 弹窗的显示与隐藏
				
				
				
				// 学生用户要问ai的问题
				question:"",
				// ai的解答
				answer:"",
				
				asking:false,
				
				
				// 错误弹窗提示信息
				errorMessage: '',
				errorPopBackgroundColor: '#ff4d4f', // 错误弹窗背景颜色
				timeoutId: null,
				
				// 侧面弹窗
				isSidebarVisible: false, 
				
				
				// 学生基本信息,从后端服务器获取
				studentInf:"",
		
		
				// “进行中的课程”
				enabled_courseList:"",
				// “待提交的作业”
				unfinished_studentJobList:"",
				
				
				// 筛选课程
				selected_enabled_courseList:[],
				selected_enabled_courseList_temp:[],
				// 筛选课程的作业
				selected_unfinished_studentJobList:[],
				
				
				
				showAskAiModal: false,
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
			
			
			this.load_studentInf(); 
			this.load_enabled_courseList();
			this.load_unfinished_studentJobList();
		},
	  
	  
	  
	  
	  
	  
		methods: {
			openAskAiModal(){
				this.showAskAiModal=true;
			},
			
			closeAskAiModal(){
				this.showAskAiModal=false;
				this.question="";
				this.answer="";
			},
			
			
			askAiRequest(){
				this.answer="",
				this.asking=true;
				uni.showLoading({
				    title: '正在思考中...', // 加载动画的提示文字
				    mask: true // 阻止点击背景时关闭加载提示
				});
				uni.request({
					url: `${this.pyapiUrl}/api/aiChat`, 
					method: 'POST',
					data:{
						text:this.question
					},
					success: (res) => {
						 // console.log(res);
						if (res.data.data === '000') {
							this.answer=res.data.text;
						} 
						else {
							this.showError("网络繁忙，请稍后再试"); // 显示错误信息
						}
					},
					fail: () => {
						this.showError("网络繁忙，请稍后再试");
					},
					complete: () => {
						this.asking=false;
						uni.hideLoading();
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
			
			
			
			formatDate(date) {
			    // 如果输入的是日期字符串，转换为 Date 对象
			    if (typeof date === 'string') {
			        date = new Date(date);
			    }
			
			    // 获取年份、月份、日期
			    const year = date.getFullYear();
			    const month = (date.getMonth() + 1).toString().padStart(2, '0'); // 月份从 0 开始，所以加 1
			    const day = date.getDate().toString().padStart(2, '0'); // 确保日期是两位数
			
			    // 返回格式化后的字符串
			    return `${year}-${month}-${day}`;
			},
			
			
			// 侧面弹窗的显示和隐藏
		    openSidebar() {
				this.selected_enabled_courseList_temp = [...this.selected_enabled_courseList];
		        this.isSidebarVisible = true;
		    },
		    closeSidebar() {
				this.selected_enabled_courseList_temp = [...this.selected_enabled_courseList];
		        this.isSidebarVisible = false; 
		    },	
			
			// 侧面弹窗里的课程按钮，点击了就变为蓝色表示筛选该课程
			toggleCourseSelection(course) {
				const index = this.selected_enabled_courseList_temp.findIndex(item => item.classId === course.classId);
				if (index !== -1) {
					this.selected_enabled_courseList_temp.splice(index, 1);
				} else {
					this.selected_enabled_courseList_temp.push(course);
				}
			},
			
			// 侧面弹窗的“保存”按钮
			confirmSelection() {
				this.selected_enabled_courseList = [...this.selected_enabled_courseList_temp];
			    const selectedCourseIds = new Set(this.selected_enabled_courseList.map(course => course.classId));
			    this.selected_unfinished_studentJobList = this.unfinished_studentJobList.filter(job =>
			        selectedCourseIds.has(job.classId)
			    );	
			    this.closeSidebar();
			},
			
			// 侧面弹窗的“重置”按钮
			resetSelection() {
				// 重置侧面弹窗的课程筛选列表
				this.selected_enabled_courseList = [...this.enabled_courseList];
				this.selected_enabled_courseList_temp = [...this.selected_enabled_courseList];
				// 重置主页的作业筛选列表
				this.selected_unfinished_studentJobList = [...this.unfinished_studentJobList];
			},
			
			
			
			

			
			// 获取学生的基本信息
			load_studentInf() {
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
			
			// 初始化课程列表
			load_enabled_courseList() {
				// if(!this.who){
				// 	// console.log('Debug: this.who is', this.who); 
				// 	this.showError("网络错误，请稍后再试");
				// 	return;
				// }
				uni.request({
					url: `${this.apiUrl}/api/queryClassByStudentId?studentId=${this.who}`,
					method: 'GET',
					success: (res) => {
						 // console.log(res);
						if (res.data.code === '000') {
							this.enabled_courseList = res.data.data;
							this.load_selected_enabled_courseList();
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
			
			
			// 初始化筛选的课程列表
			load_selected_enabled_courseList() {
				this.selected_enabled_courseList = [...this.enabled_courseList];
			},
			
			
			// 初始化作业列表
			load_unfinished_studentJobList() {
				// if(!this.who){
				// 	// console.log('Debug: this.who is', this.who); 
				// 	this.showError("网络错误，请稍后再试");
				// 	return;
				// }
				uni.request({
					url: `${this.apiUrl}/student/queryJobByStudentJobFactor`, 
					method: 'POST',
					data:{
						jobId: "",
						studentId: this.who,
						status: ""
					},
					success: (res) => {
						 // console.log(res);
						if (res.data.code === '000') {
							this.unfinished_studentJobList = res.data.data;
							this.load_selected_unfinished_studentJobList();
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
			
			
			// 初始化筛选的课程的课程的作业列表
			load_selected_unfinished_studentJobList() {
				this.selected_unfinished_studentJobList= [...this.unfinished_studentJobList];
			},
			
			
			
			goToJobDetail(jobId) {
				uni.navigateTo({
					url: `/pages/index/student/jobDetail?jobId=${jobId}&id=${this.who}`  
				});
			},
			
			
			goToCourseDetail(classId) {
				uni.navigateTo({
					url: `/pages/index/student/courseDetail?classId=${classId}&id=${this.who}`  
				});
			},
			
			
			// 底部导航栏按钮
			// goToHome() {
			// 	uni.pageScrollTo({
			// 		scrollTop: 0, // 滚动到页面顶部
			// 		duration: 500, // 滚动动画的持续时间（毫秒）
			// 	});
			// },
			// goToCourses() {
			// 	uni.redirectTo({
			// 		url: `/pages/index/student/student2?id=${this.who}`  // 添加 id 参数
			// 	});

			// },
			// goToProfile() {
			// 	uni.redirectTo({
			// 		url: `/pages/index/student/student3?id=${this.who}`  // 添加 id 参数
			// 	});

			// },
			
			// 底部点击导航栏按钮切换页面
			goToHome() {
				uni.pageScrollTo({
					scrollTop: 0, // 滚动到页面顶部
					duration: 500, // 滚动动画的持续时间（毫秒）
				});
			
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