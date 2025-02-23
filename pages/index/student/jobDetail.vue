<style scoped>
	.student-page {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		width: 637.5rpx;
		margin: auto;
	}
	
	.text-area {
	  width: 100%;
	  text-align: left;
	  padding-left: 0rpx;
	  font-size: 28rpx;
	  font-weight: bold;
	  margin-bottom: 20rpx;
	  margin-top:90rpx;
	}
	
	.text{
		font-size:35rpx; 
	}
	
	
	.text-area1 {
	  width: 100%;
	  text-align: left;
	  padding-left: 0rpx;
	  font-size: 28rpx;
	  font-weight: bold;
	  margin-bottom: 20rpx;
	  margin-top:0rpx;
	}
	
	.text1{
		font-size:32rpx; 
	}
	
	
	.text-area2 {
	  width: 100%;
	  text-align: left;
	  padding-left: 0rpx;
	  font-size: 28rpx;
	  font-weight: bold;
	  margin-bottom: 20rpx;
	  margin-top:20rpx;
	}
	
	.text2{
		font-size:28rpx; 
		color:gray;
	}
	
	.text-area3 {
	  width: 100%;
	  text-align: left;
	  padding-left: 3rpx;
	  font-size: 33rpx;
	  font-weight: bold;
	  margin-bottom: 30rpx;
	  margin-top:30rpx;
	}
	
	.text3{
		font-size:33rpx; 
		color:black;
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
	
	

	.job-detail {
		width: 100%;
		padding: 20rpx;
	}

	.job-title {
		font-size: 42rpx;
		font-weight: bold;
		margin-bottom: 20rpx;
		margin-top:30rpx;
	}

	.job-info {
		font-size: 28rpx;
		color: #666;
		margin-bottom: 15rpx;
	}
	.job-content {
		font-size: 26rpx;
		/* color: #333; */
		color:black;
		border:1px solid lightgray;
		min-height:200rpx;
		padding:20rpx 20rpx;
		border-radius:10rpx;
		overflow-y: auto;/* 当作业内容过长时出现滚动条 */
	}
	
	
	
	.job-text{
		min-height: 400rpx;
		overflow-x: auto;
		overflow-y: auto;
		padding: 10rpx;
		background-color: #f5f5f5;
		border-radius: 5rpx;
		border: 1px solid #ccc;
		font-family: "Courier New", monospace;
		white-space: nowrap;  /* 禁止换行 */
		margin-bottom:50rpx;
	}
	
	.highlight-code{
		min-height: 400rpx;
		overflow-x: auto;
		overflow-y: auto;
		padding: 10rpx;
		background-color: #1f1f1f;
		background-color: #f5f5f5;
		border-radius: 5rpx;
		border: 1px solid #ccc;
		font-family: "Courier New", monospace;
		white-space: pre;  /* 保留换行和空格 */
		margin-bottom:100rpx;
		/* color:white; */
	}
	.submit-button {
		background-color: #555555;
		color: white;
		width: 200rpx;
		height: 60rpx;
		border: none;
		border-radius: 10rpx;
		font-size: 28rpx;
		text-align: center;
		line-height: 60rpx;
		margin-top: 40rpx;
		cursor: pointer;
		margin-bottom:120rpx;
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
	

</style>




<template>
	<view class="student-page">
		<view class="error-pop" :class="{ active: this.errorMessage }" :style="{ backgroundColor: errorPopBackgroundColor }">{{ this.errorMessage }}</view>
		
		
		<view class="job-detail">
			<!-- 显示作业信息 -->
			<view class="job-title">作业标题：{{ job.title }}</view>
			
			<view class="text-area3">
			    <text class="text3">作业状态：</text>
				<text v-if="this.jobStatus === 'created'" class="text3" :style="{ color: 'red' }">未提交</text>
				<text v-else-if="this.jobStatus === 'submitted'" class="text3" :style="{ color: 'seagreen' }">已提交</text>
			</view>
			
			
			<view class="job-info">作业开始时间：{{ formatDate1(job.startTime) }} </view>
			<view class="job-info">作业截止时间：{{ formatDate1(job.endTime) }} </view>
			
			
			<view class="text-area2">
			    <text class="text2">(移动端不支持附件提交，请使用网页端提交附件)</text>
			</view>
			
			
			
			
			<view class="text-area">
			    <text class="text">作业内容</text>
			</view>
			<!-- <view class="job-content">{{ job.content }}</view> -->
			<view class="job-content" v-html="job.content"></view>

			<!-- 显示用户提交的作业 -->
			<view class="text-area">
			    <text class="text">我的代码</text>
			</view>

			<!-- 用户输入代码 -->
			<textarea v-model="jobText" placeholder="请输入代码..." class="job-text"></textarea>


			<view class="text-area1">
			    <text class="text1">代码高亮预览</text>
			</view>
			
			<!-- 显示高亮后的代码 -->
			<view class="highlight-code" v-html="highlightCode(jobText)"></view>
			

			
			<!-- “提交作业”按钮 -->
			<button class="submit-button" @click="handleSubmitJob">提交作业</button>
			
			
			
			
			<!-- 提交作业确认弹窗 -->
			<view v-if="showSubmitConfirmationModal" class="modal-overlay">
			  <view class="modal-content">
				<text>您确定要提交代码吗？</text>
				<view class="modal-buttons">
				  <button class="modal-button confirm-button" @click="submitJobRequest">确认</button>
				  <button class="modal-button cancel-button" @click="closeSubmitConfirmationModal">取消</button>
				</view>
			  </view>
			</view>
			
		</view>
	</view>
</template>




<script>
import Prism from 'prismjs';
import 'prismjs/themes/prism.css';  // 你可以选择不同的主题



import 'prismjs/components/prism-javascript.min.js';  // JavaScript支持


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
			
			
			// 作业详情
			job: {},
			jobId:"",
			jobStatus:"",
			
			
			// 用户输入的代码文本
			jobText: '', 
			// 高亮代码
			highlightedCode: '',
			
			
			
			// 提交作业确认弹窗
			showSubmitConfirmationModal: false, 
			
		};
	},

	onLoad(query) {
		// 获取 jobId
		this.jobId = query.jobId;
		
		// 获取用户id
		console.log(query.id);
		this.who=query.id;
		
		
		console.log('jobId',this.jobId);
		
		if(!this.who){
			// console.log('Debug: this.who is', this.who); 
			this.showError("请先登录！");
			uni.reLaunch({
				// (url后期需要修改！！！)
			    url: "/pages/index/login"
			});
			return;
		}
		
		
		// 直接加载作业详情（模拟后端请求）
		this.loadJobDetail();
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
		
		
		
		

		// 代码高亮
		highlightCode(code) {
		    return Prism.highlight(code, Prism.languages.javascript, 'javascript');
		},
		
		
		
		
		// 提交作业
		handleSubmitJob(){
			if(!this.who){
				// console.log('Debug: this.who is', this.who); 
				this.showError("请先登录！");
				return;
			}
			
			if (!this.jobText) {
			    this.showError("作业内容不能为空！");
			    return;
			}
			this.showSubmitConfirmationModal = true;
		},
		closeSubmitConfirmationModal() {
			this.showSubmitConfirmationModal = false;
		},
		
		
		submitJobRequest(){
			    uni.showLoading({
			        title: '正在提交中...',
			        mask: true // 防止用户点击其他区域
			    });
			
			    const requestData = {
			        jobText: this.jobText,   // 提交的作业文本
			        studentId: this.who,     // 当前学生的ID
			        jobId: this.jobId        // 作业ID
			    };
			
			    uni.request({
			        url: `${this.apiUrl}/api/submitJobText`,  // 请求的URL
			        method: 'POST',
			        data: requestData,
			        success: (res) => {
						// console.log(res);
			            if (res.data.code=== '000') {
							this.showError("作业提交成功！","#28a745");
			                uni.showToast({
			                    title: '提交成功',
			                    icon: 'success',
			                    duration: 1000
			                });
							this.loadJobDetail();
							// this.jobText="";
			            } else {
			                this.showError(res.data.info || '提交失败，请稍后再试');
			            }
			        },
			        fail: (err) => {
			            this.showError("网络错误，请稍后再试");
			        },
					complete: () => {
						uni.hideLoading();
						this.closeSubmitConfirmationModal();
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
		
		
		
		loadJobDetail() {
			// if(!this.who){
			// 	// console.log('Debug: this.who is', this.who); 
			// 	this.showError("网络错误，请稍后再试");
			// 	return;
			// }
			uni.request({
				url: `${this.apiUrl}/teacher/queryJobByFactor`, 
				method: 'POST',
				data:{
					"jobId": this.jobId
				},
				success: (res) => {
					 // console.log(res);
					if (res.data.code === '000') {
						this.job=res.data.data[0];
						
						
						
							uni.request({
								url: `${this.apiUrl}/api/queryStudentJobByFactor`, 
								method: 'POST',
								data:{
									"jobId": this.jobId,
									"studentId": this.who,
								},
								success: (res) => {
									 // console.log(res);
									if (res.data.code === '000') {
										if(res.data.data.length === 0){
											this.jobStatus='created';
										}
										else{
											this.jobStatus=res.data.data[0].status;
										}
										
										// console.log('status',this.jobStatus);
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
		}
		
		
		
	}
};
</script>


