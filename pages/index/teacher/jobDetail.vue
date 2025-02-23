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
	  margin-top:50rpx;
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
	
	.text-area4 {
	  width: 100%;
	  text-align: left;
	  padding-left: 5rpx;
	  margin-bottom: 15rpx;
	  margin-top:10rpx;
	}
	
	.text4{
		font-size:27rpx; 
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
	
	.job-title1 {
		font-size: 33rpx;
		font-weight: bold;
		margin-bottom: 20rpx;
		margin-top:30rpx;
		padding-left:10rpx;
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
	
	

	.charts{
		margin-left:-55rpx;
		margin-top:30rpx;
		width: 750rpx;
		height: 500rpx;
	}

</style>




<template>
	<view class="student-page">
		<view class="error-pop" :class="{ active: this.errorMessage }" :style="{ backgroundColor: errorPopBackgroundColor }">{{ this.errorMessage }}</view>
		
		
		<view class="job-detail">
			<!-- 显示作业信息 -->
			<view class="job-title">作业标题：{{ job.title }}</view>
			
			<view class="job-title1">课程班级：{{ this.className }}</view>
			
			<view class="job-info">作业开始时间：{{ formatDate1(job.startTime) }} </view>
			<view class="job-info">作业截止时间：{{ formatDate1(job.endTime) }} </view>
			
			

			
			<view class="text-area">
			    <text class="text">作业内容</text>
			</view>
			<!-- <view class="job-content">{{ job.content }}</view> -->
			<view class="job-content" v-html="job.content"></view>


			<view class="text-area">
			    <text class="text">作业提交状况统计</text>
			</view>
			
			<view class="text-area4">
			    <text class="text4">课程班级总人数：{{sumNum}}</text>
			</view>
			
			<view class="text-area4">
			    <text class="text4">已提交作业人数：{{submitNum}}</text>
			</view>
			
			<view class="text-area4">
			    <text class="text4"><text style="color: red;">未提交作业人数：</text><text style="color: red;">{{sumNum-submitNum}}</text></text>
			</view>
			
			<view>
				<canvas canvas-id="EUWRpWbGRtMVSOsHeBwXnDWUYFYQjOGo" id="EUWRpWbGRtMVSOsHeBwXnDWUYFYQjOGo" class="charts" @touchend="tap"/>
			</view>
			
		</view>
	</view>
</template>




<script>

import { config } from '../../../config'; // 导入 config.js 文件
import uCharts from '@/uni_modules/qiun-data-charts/js_sdk/u-charts/u-charts.js';
var uChartsInstance = {};


export default {
	data() {
		return {
			apiUrl: `http://${config.host}:${config.port}`, // 使用配置的host和port
			pyapiUrl: `http://${config.host}:${config.pyport}`, // 使用配置的host和port
			
			who:"",
			
			
			// 错误弹窗提示信息
			errorMessage: '',
			errorPopBackgroundColor: '#ff4d4f', // 错误弹窗背景颜色
			timeoutId: null,
			
			
			job: {},
			jobId:"",
			classId:"",
			
			className:"",
			 
			// 班级总人数
			sumNum:0,
			// 提交的人数
			submitNum:0,
			
			
			// 画板大小
			cWidth: 750,
			cHeight: 500,
		};
	},
	


	onLoad(query) {
		// 获取用户id
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
		
		
		
		
		
		
		// 获取 jobId
		this.jobId = query.jobId;
		console.log('jobId',this.jobId);
		
		
		// 获取 classId
		// this.classId=query.classId;
		

		
		this.loadJobDetail();
		
		this.loadClassId();
		
		
		
		//这里的 750 对应 css .charts 的 width
		this.cWidth = uni.upx2px(750);
		//这里的 500 对应 css .charts 的 height
		this.cHeight = uni.upx2px(500);
		// this.getServerData();
		
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
		
		
		loadClassId(){
			uni.request({
				url: `${this.apiUrl}/teacher/queryJobByFactor`, 
				method: 'POST',
				data:{
					"jobId": this.jobId
				},
				success: (res) => {
					 console.log(res);
					if (res.data.code === '000') {
						this.classId=res.data.data[0].classId;
						this.loadClassDetail();
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
		
		
		loadJobstatistics(){
			uni.request({
				url: `${this.pyapiUrl}/api/queryJobCommitRate`, 
				method: 'POST',
				data:{
					"job_id": this.jobId
				},
				success: (res) => {
					 // console.log(res);
					if (res.data.code === '000') {
						this.submitNum=res.data.submitted;
						console.log('班级提交人数',this.submitNum);
						
						this.getServerData();
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
		
		
		
		
		loadJobDetail() {
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
		
		
		
		loadClassDetail(){
			uni.request({
				url: `${this.apiUrl}/teacher/queryClassByFactor`,
				method: 'POST',
					data:{
						classId:this.classId
					},
				success: (res) => {
					 // console.log(res);
					if (res.data.code === '000') {
						this.sumNum=res.data.data[0].peopleCount;
						this.className=res.data.data[0].name;
						console.log('班级名称',this.className);
						console.log('班级总人数',this.sumNum);
						this.loadJobstatistics();
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
		
		
		
		
		getServerData() {
			const a=this.submitNum;
			const b=this.sumNum-this.submitNum;
			let res;
		  //模拟从服务器获取数据时的延时
		  setTimeout(() => {
			  if(a===0){
				  //模拟服务器返回数据，如果数据格式和标准格式不同，需自行按下面的格式拼接
				  res = {
				  		series: [
				  		  {
				  			  
				  				data: 	[	
				  							{"name":"未提交","value":b},
				  							// {"name":"已提交","value":a},
				  							
				  							// {"name":"三班","value":20},
				  							// {"name":"四班","value":18},
				  							// {"name":"五班","value":8},
				  						]
				  		  }
				  		]
				    };
			  }
			  else{
				  res = {
				  		series: [
				  		  {
				  			  
				  				data: 	[	
				  							{"name":"未提交","value":b},
				  							{"name":"已提交","value":a},
				  							
				  							// {"name":"三班","value":20},
				  							// {"name":"四班","value":18},
				  							// {"name":"五班","value":8},
				  						]
				  		  }
				  		]
				    };
			  }

		    this.drawCharts('EUWRpWbGRtMVSOsHeBwXnDWUYFYQjOGo', res);
		  }, 0);
		},
		drawCharts(id,data){
		  const ctx = uni.createCanvasContext(id, this);
		  uChartsInstance[id] = new uCharts({
		    type: "pie",
		    context: ctx,
		    width: this.cWidth,
		    height: this.cHeight,
		    series: data.series,
		    animation: true,
		    timing: "easeOut",
		    duration: 1000,
		    rotate: false,
		    rotateLock: false,
		    background: "#FFFFFF",
		    // color: ["#1890FF","#91CB74","#FAC858","#EE6666","#73C0DE","#3CA272","#FC8452","#9A60B4","#ea7ccc"],
			color: ["#EE6666","#1890FF","#73C0DE","#3CA272","#FC8452","#9A60B4","#ea7ccc"],
		    padding: [5,5,5,5],
		    fontSize: 13,
		    fontColor: "#666666",
		    dataLabel: true,
		    dataPointShape: true,
		    dataPointShapeType: "solid",
		    touchMoveLimit: 60,
		    enableScroll: false,
		    enableMarkLine: false,
		    legend: {
		      show: true,
		      position: "bottom",
		      float: "center",
		      padding: 5,
		      margin: 5,
		      backgroundColor: "rgba(0,0,0,0)",
		      borderColor: "rgba(0,0,0,0)",
		      borderWidth: 0,
		      fontSize: 13,
		      fontColor: "#666666",
		      lineHeight: 11,
		      hiddenColor: "#CECECE",
		      itemGap: 10
		    },
		    extra: {
		      pie: {
		        activeOpacity: 0.5,
		        activeRadius: 10,
		        offsetAngle: 0,
		        labelWidth: 15,
		        border: true,
		        borderWidth: 3,
		        borderColor: "#FFFFFF",
		        customRadius: 0,
		        linearType: "none"
		      },
		      tooltip: {
		        showBox: true,
		        showArrow: true,
		        showCategory: false,
		        borderWidth: 0,
		        borderRadius: 0,
		        borderColor: "#000000",
		        borderOpacity: 0.7,
		        bgColor: "#000000",
		        bgOpacity: 0.7,
		        gridType: "solid",
		        dashLength: 4,
		        gridColor: "#CCCCCC",
		        boxPadding: 3,
		        fontSize: 13,
		        lineHeight: 20,
		        fontColor: "#FFFFFF",
		        legendShow: true,
		        legendShape: "auto",
		        splitLine: true,
		        horizentalLine: false,
		        xAxisLabel: false,
		        yAxisLabel: false,
		        labelBgColor: "#FFFFFF",
		        labelBgOpacity: 0.7,
		        labelFontColor: "#666666"
		      }
		    }
		  });
		},
		tap(e){
		  uChartsInstance[e.target.id].touchLegend(e);
		  uChartsInstance[e.target.id].showToolTip(e);
		}
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
	}
};
</script>


