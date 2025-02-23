<style scoped>
	.admin-page {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		width:637.5rpx;
		margin: auto; 
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
		padding-top:40rpx;
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: center;
		width: 100%; 
		padding-bottom:50rpx;
	}
	
	
	
	.text-area{
		width: 100%; 
		text-align: left; 
		padding-left: 20rpx; 
		font-size: 28rpx; 
		font-weight: bold; 
		/* margin-bottom: 20rpx; */
		padding-bottom: 20rpx; 
		display:flex;
		flex-direction:row;
	}
	
	.text{
		font-size:35rpx; 
		flex-grow: 1; /* 占据剩余空间，让行内剩余元素紧靠右侧 */
	}
	
	
	.placeholder-text {
	  font-size: 28rpx;
	  color: gray; 
	}

	
	
	
	.semester-list-section1 {
	    display: flex;
	    flex-direction: column;
	    align-items: center;
	    justify-content: center;
	    width: 100%;
		border:1px solid gray;
		border-radius: 20rpx;
		height:300rpx;
		margin-bottom:60rpx;
		/* padding-top:11rpx; */
	}
	
	.semester-list-section {
	    display: flex;
	    flex-direction: column;
	    align-items: center;
	    justify-content: center;
	    width: 100%;
		border:1px solid gray;
		border-radius: 20rpx;
		height:auto;
		min-height:300rpx;
		margin-bottom:20rpx;
	}
	
	.semester-item {
		display: flex;
		flex-direction: column;
	    width: 90%;
	    padding: 20rpx;
	    background-color: #f9f9f9;
		margin-top:20rpx;
	    margin-bottom: 30rpx;
	    border-radius: 15rpx;
	    box-shadow: 0 2rpx 6rpx rgba(0, 0, 0, 0.1);
		opacity: 0;  /* 初始透明 */
		animation: slideIn 0.5s ease forwards;  /* 滑入动画 */
	}
	
	.semester-item1 {
		display: flex;
		flex-direction: column;
	    width: 90%;
	    padding: 20rpx;
	    background-color: #f9f9f9;
	    border-radius: 15rpx;
	    box-shadow: 0 2rpx 6rpx rgba(0, 0, 0, 0.1);
		opacity: 0;  /* 初始透明 */
		animation: slideIn 0.5s ease forwards;  /* 滑入动画 */
		/* height:200rpx; */
	}
	
	
	
	/* 学期名称 */
	.semester-name {
	    font-size: 30rpx;
	    font-weight: bold;
	    margin-bottom: 20rpx;
	}
	
	.semester-name1 {
	    font-size: 32rpx;
	    font-weight: bold;
	    margin-bottom: 50rpx;
	}
	
	
	/* 学期日期 */
	.semester-dates {
	    font-size: 26rpx;
	    color: #666666;
	}
	.semester-dates text {
	    display: block; /* 让每个text标签换行显示 */
	    margin-bottom: 5rpx;
	}
	.semester-dates1 {
	    font-size: 28rpx;
	    color: #666666;
	}
	.semester-dates1 text {
	    display: block; /* 让每个text标签换行显示 */
	    margin-bottom: 5rpx;
	}
	
	
	/* 学期状态(启用/停用？) */
	.semester-status {
	    margin-top: 10rpx;
	}
	
	
	/* 启用/停用按钮 */
	.status-button {
		width: 240rpx; 
		height: 60rpx; 
	    border-radius: 20rpx;
	    cursor: pointer;
		font-size:32rpx;
		display: flex; 
		align-items: center; 
		justify-content: center; 
		text-align: center; 
	}
	.status-button.active {
	    /* background-color: #4caf50; */
		background-color:lightseagreen;
	    color: white;
	}
	.status-button.inactive {
	    background-color: #f44336;
	    color: white;
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
	
	
	
	
	/* 创建学期按钮 */
	.create-semester-button {
		/* (url后期需要修改！！！) */
		background-image: url('/static/createSemesterButton.png'); 
	    width: 150rpx;
	    height: 50rpx;
	    cursor: pointer;
		background-size: cover;
		background-position: center 30%; 
		border:1px solid transparent;
		outline: none; 
		/* border:1px solid black; */
	}
	
	.create-semester-button:after{
		border: none; 
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
</style>






<template>
	<view class="admin-page">
		<view class="error-pop" :class="{ active: this.errorMessage }" :style="{ backgroundColor: errorPopBackgroundColor }">{{ this.errorMessage }}</view>

		<view class="header">
		    <text class="text">您好！尊敬的管理员</text>
		</view>
		
		
		
		<view class="text-area">
		  <text class="text">进行中的学期</text>
		</view>
		
		
		
		<!-- 进行中的学期 -->
		<view class="semester-list-section1">
		  <view class="semester-item1" v-if="who">
			<text class="semester-name">{{ this.activeSemester.name }}</text>
			<text class="semester-dates">
			<text>学期编号: {{ this.activeSemester.semesterId }}</text>
			  <text>开始时间: {{ formatDate(this.activeSemester.startTime) }}</text>
			  <text>结束时间: {{ formatDate(this.activeSemester.endTime) }}</text>
			</text>
			<view class="semester-status">
			  <button
				@click="viewAllCourses"
				class="status-button inactive"
			  >课程管理</button>
			</view>
		  </view>
		</view>

		

		<view class="text-area">
		  <text class="text">已结束或未开始的学期</text>
		  <button @click="handleCreateSemester" class="create-semester-button"></button>
		</view>
		
		
		
		<!-- 已结束或未开始的学期 -->
		<view class="semester-list-section">
		  <view class="semester-item" v-for="(semester, index) in inactiveSemesterList" :key="index">
			<text class="semester-name">{{ semester.name }}</text>
			<text class="semester-dates">
				<text>学期编号: {{ semester.semesterId }}</text>
				<text>开始时间: {{ formatDate(semester.startTime) }}</text>
				<text>结束时间: {{ formatDate(semester.endTime) }}</text>
			</text>
			<view class="semester-status">
			  <button
				@click="openFirstConfirmationModal(semester.semesterId,semester.name)"
				class="status-button active"
			  >启用</button>
			</view>
		  </view>
		</view>
		
		
		
		
		
		
		<!-- 第一个确认弹窗 -->
		<view v-if="showFirstConfirmationModal" class="modal-overlay">
		  <view class="modal-content">
		    <text>您确定要将 <text style="color: red;">{{ this.selectedSemesterName }}</text> <br>更改为 <text style="color: red;">启用</text> 状态吗?</text>
		    <view class="modal-buttons">
		      <button class="modal-button confirm-button" @click="openSecondConfirmationModal">确认</button>
		      <button class="modal-button cancel-button" @click="closeFirstConfirmationModal">取消</button>
		    </view>
		  </view>
		</view>
		
		
		
		<!-- 第二个确认弹窗 -->
		<view v-if="showSecondConfirmationModal" class="modal-overlay">
		  <view class="modal-content">
		    <text>您确认要对当前学期执行此操作吗？<br><text style="color: red;">（ 当前操作一旦执行便无法撤销 ! ）</text></text>
		    <view class="modal-buttons">
		      <button class="modal-button confirm-button" @click="confirmChangeStatus">确认</button>
		      <button class="modal-button cancel-button" @click="closeSecondConfirmationModal">取消</button>
		    </view>
		  </view>
		</view>
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		<!-- 创建学期弹窗 -->
		<view v-if="showCreateSemesterModal" class="modal-overlay"  v-show="modalVisible">
		  <view class="modal-content1">
		    <text class="info-label">学期名称：</text>
		    <input class="info-input1" v-model="semesterName" placeholder="请输入学期名称" />
		
		
		
		    <!-- 选择开始时间 -->
			<view class="flex-row">
				<text class="info-label">学期开始时间：</text>
				<picker mode="date"   :value="startDate" start="2020-01-01" end="2030-12-31" @change="handleStartDateChange"  @cancel="handlePickerCancel">
					<button class="selectDate-button" @click="hideModalOverlay">点击选择开始时间</button>
				</picker>
			</view>
			<view class="info-input1">
				<span v-if="!startDate" class="placeholder-text">请选择学期开始时间</span>
				<span v-else>{{ startDate }}</span>
			</view>



            <!-- 选择结束时间 -->
			<view class="flex-row">
				<text class="info-label">学期结束时间：</text>
				<picker mode="date" :value="endDate" start="2020-01-01" end="2030-12-31" @change="handleEndDateChange"  @cancel="handlePickerCancel">
					<button class="selectDate-button" @click="hideModalOverlay">点击选择结束时间</button>
				</picker>
			</view>
			<view class="info-input1"><!-- {{ endDate || '请选择学期结束时间'}} -->
				<span v-if="!endDate" class="placeholder-text">请选择学期结束时间</span>
				<span v-else>{{ endDate }}</span>
			</view>
		
		
		
		
		    <view class="modal-buttons">
		      <button class="modal-button confirm-button1" @click="submitCreateSemester">确认</button>
		      <button class="modal-button cancel-button"  @click="closeCreateSemesterModal">取消</button>
		    </view>
		  </view>
		</view>

		
		
		
		
		
		
		<!-- 底部导航栏 -->
		<!-- 添加一段空白挤占空间，防止footer底部导航栏遮挡住最下面的作业 -->
		<view class="footer-blank"></view>
		<view class="footer">
			<view class="footer-item" @click="goToHome">
				<view class="icon">📅</view>
				<view class="text" style="color:#ff4d4f">学期管理</view>
			</view>
			<view class="footer-item" @click="goToTeachers">
				<view class="icon">🧑‍🎓</view>
				<view class="text">教师管理</view>
			</view>
			<view class="footer-item" @click="goToProfile">
				<view class="icon">👤</view>
				<view class="text">系统管理</view>
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
				
				

				// 处于“启用”状态的学期
				activeSemester:[],
				// 处于“停用”状态的学期列表
				inactiveSemesterList:[],
				
				
				

				
				
				
				// “启用”学期或“停用”学期的确认页面
				showFirstConfirmationModal: false, 
				showSecondConfirmationModal: false,
				selectedSemesterId: "", 
				selectedSemesterName:"",
				
				
				
				// “创建”学期操作:输入创建学期信息
				semesterName: '',
				startDate: '', 
				endDate: '', 
				
				
				
				showCreateSemesterModal: false,  
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
			
			this.loadAdminInf();
			this.loadInactiveSemesterList();
			this.loadActiveSemesterList();
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
			
			
			
			
			
			
			
			
			// 创建学期弹窗		
			handleCreateSemester() {
				if(!this.who){
					// console.log('Debug: this.who is', this.who); 
					this.showError("请先登录！");
					return;
				}
				this.showCreateSemesterModal = true;  
			},
			
			
			
			// 点击确认按钮提交创建学期表单
			submitCreateSemester() {
				// 判断学期名，年月日是否为空
				if (!this.semesterName || !this.startDate || !this.endDate) {
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
				this.createSemesterRequest();
			},
			
			
			createSemesterRequest(){
				// 构建学期数据对象
				const semesterData = {
					name: this.semesterName,
					startTime: this.startDate,
					endTime: this.endDate,
				};
				// 向服务器发送 POST 请求创建学期
				uni.showLoading({
				    title: '正在创建新学期...', // 加载动画的提示文字
				    mask: true // 阻止点击背景时关闭加载提示
				});
				uni.request({
					url: `${this.apiUrl}/admin/createSemester`, 
				    method: 'POST',
				    data: semesterData, // 发送学期数据
				    success: (res) => {
						if (res.data.code === '000') {
							this.showError("学期创建成功！", "#28a745");
							
							this.loadInactiveSemesterList();
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
						this.closeCreateSemesterModal(); // 关闭创建学期弹窗
						// 隐藏加载动画
						uni.hideLoading();
					}
				});
			},
			
			
			resetCreateSemesterFields() {
			    this.semesterName = '';
			    this.startDate = '';
			    this.endDate = '';
			},
			
			
			isValidDate(year, month, day) {
			  const date = new Date(year, month - 1, day); // 月份减 1
			  return date.getFullYear() === parseInt(year) &&
			         date.getMonth() === (parseInt(month) - 1) &&
			         date.getDate() === parseInt(day);
			},
			
			
			
			// 点击取消按钮取消创建学期表单
			closeCreateSemesterModal() {
			    this.showCreateSemesterModal = false; 
			    this.resetCreateSemesterFields(); 
			},

			
			
			
			
			loadAdminInf(){
				
			},
			
			
			
			
			
			// 获取未启用学期的列表
			loadInactiveSemesterList(){
				uni.request({
				    url: `${this.apiUrl}/admin/queryAllSemester`, 
				    method: 'GET',
				    success: (res) => {
						 // console.log(res);
				        if (res.data.code === '000') {
							this.inactiveSemesterList = res.data.data;
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
			loadActiveSemesterList(){
				uni.request({
				    url: `${this.apiUrl}/admin/queryCurrentSemester`, 
				    method: 'GET',
				    success: (res) => {
						 // console.log(res);
				        if (res.data.code === '000') {
							this.activeSemester = res.data.data;
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
			
			

			
			
			

			
			
			
			// 学期状态切换
			setCurrentSemesterRequest() {
				uni.showLoading({
					title: '正在启用学期...', // 加载动画的提示文字
					mask: true // 阻止点击背景时关闭加载提示
				});
				uni.request({
					url: `${this.apiUrl}/admin/setCurrentSemester?semesterId=${this.selectedSemesterId}`,  // 在 URL 中直接传递查询参数
					method: 'GET',  
					success: (res) => {
						//console.log(res);
				        if (res.data.code === '000') {
							this.showError("学期启用成功！", "#28a745");
							this.loadActiveSemesterList();
							this.loadInactiveSemesterList();
							uni.showToast({
							    title: '修改成功',  // 提示的文本
							    icon: 'success',       // 可选值：'success', 'loading', 'none'，分别表示成功提示、加载提示和没有图标的提示
							    duration: 1000      // 提示框的显示时长，单位毫秒，默认2000ms
							});
				        } 
						else {
							this.showError(res.data.info); // 显示错误信息
				        }
					},
					fail: () => {
						this.showError("网络错误，请稍后再试");
					},
					complete: () => { 
						uni.hideLoading();
						this.closeSecondConfirmationModal();  
					}
				});
			},
			
			
			
			
			
			// 确认更改学期状态
			confirmChangeStatus() {
				this.setCurrentSemesterRequest();
			},


			
			// 打开第一个确认弹窗
			openFirstConfirmationModal(semesterId, Name) {
			    this.selectedSemesterId = semesterId;
				this.selectedSemesterName = Name;
			    this.showFirstConfirmationModal = true;
			},
			
			// 打开第二个确认弹窗
			openSecondConfirmationModal() {
			    this.showFirstConfirmationModal = false;  
			    this.showSecondConfirmationModal = true;  
			},
			
			// 关闭第一个确认弹窗
			closeFirstConfirmationModal() {
			    this.showFirstConfirmationModal = false;
			    this.selectedSemesterId = "";
				this.selectedSemesterName="";
			},
			
			// 关闭第二个确认弹窗
			closeSecondConfirmationModal() {
			    this.showSecondConfirmationModal = false;
			    this.selectedSemesterId = "";
				this.selectedSemesterName="";
			},
			
			
			viewAllCourses(){
				uni.navigateTo({
				  url: `/pages/index/admin/courses?activeSemesterId=${this.activeSemester.semesterId}&id=${this.who}`
				});


			},
			
			
			
			// 底部点击导航栏按钮切换页面
			// goToHome() {
			// 	uni.pageScrollTo({
			// 		scrollTop: 0, 
			// 		duration: 500, 
			// 	});
			// },
			// goToTeachers() {
			// 	uni.redirectTo({
			// 		url: `/pages/index/admin/admin2?id=${this.who}`  // 添加 id 参数
			// 	});
			// },

			// goToProfile() {
			// 	uni.redirectTo({
			// 		url: `/pages/index/admin/admin3?id=${this.who}`  // 添加 id 参数
			// 	});
			// }
			
			
			
			
			
			goToHome() {
				uni.pageScrollTo({
					scrollTop: 0, // 滚动到页面顶部
					duration: 500, // 滚动动画的持续时间（毫秒）
				});
			
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
