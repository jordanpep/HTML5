<template>

	<view>

		<!-- 头部搜索，定位栏 -->
		<view class="head">
			<view class="view1">
				<!-- 包裹 头部搜索，定位栏 -->
				<view style=" float: left;height: 60rpx;width:100rpx;text-align: center;">
					<view style="height: 30rpx;">
						<text class="lg text-gray" :class="'cuIcon-locationfill'" id="location"></text><!-- location为用户位置定位 -->
					</view>
					<view style="font-size: 20rpx;height: 30rpx;">
						<text style="font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">长春</text>
					</view>
				</view>

				<view style="width: 450rpx; float: left;padding-left: 15rpx;padding-right: 5rpx;">
					<input placeholder="查询服务" class="input_search_service" type="text" />
				</view>

				<button class="cu-btn  lg btn_search_service" style="float: left;">搜索</button>
				<view style="clear: both;"></view>
			</view>
		</view>

		<!-- 具体内容部分，一个分类的列表 background-color: #886666;-->
		<view style="padding-top: 30rpx;padding-bottom: 30rpx;">
			
			<view style="background-color: #8799A3;"><!-- 第一个服务 -->
				<view style="font-size: 40rpx;font-weight: 500;color: #FFFFFF;padding-top: 30rpx;padding-bottom: 30rpx;"><!-- 标题，下拉框 -->
					<view style="overflow: hidden;"><!-- 使得标题，下拉框水平 -->
						
						<view style="float: left;padding-left: 60rpx;height: 60rpx;">
							<text>上门安装</text>
						</view>
						
						<view style="float: right;padding-right: 60rpx;height: 60rpx;padding-top: 10rpx;">
							<text class="lg text-gray" :class="'cuIcon-unfold'" id="unfold1"@tap="unfold1()"></text>
						</view>
						
						<view style="clear: both;"></view>
						
					</view>
				</view>
				
				<!-- 下拉框显示的内容 -->
				<view id="consent1" style="display:none;" >
					<view style="padding-top: 30rpx;padding-bottom: 10rpx; "><!-- background-color: #6739B6; -->
						
						<view class="cu-list grid col-3">
							<view class="cu-item">
								<navigator url="../release/release"><text>宜家组装</text></navigator>
							</view>
							<view class="cu-item">
								<navigator url="../release/release"><text>厨卫安装</text></navigator>
							</view>
							<view class="cu-item">
								<navigator url="../release/release"><text>灯具安装</text></navigator>
							</view>
							<view class="cu-item">
								<navigator url="../release/release"><text>柜类安装</text></navigator>
							</view>
							<view class="cu-item">
								<navigator url="../release/release"><text>床类安装</text></navigator>
							</view>
							<view class="cu-item">
								<navigator url="../release/release"><text>座椅安装</text></navigator>
							</view>
						</view>
						
					</view>
				</view><!-- 下拉框显示的内容 -->
				
			</view><!-- 第一个服务 -->
			
			<view style="height: 10rpx;"></view><!-- 每个服务的间隔 -->
			
			<view style="background-color: #8799A3;"><!-- 第二个服务 -->
				<view style="font-size: 40rpx;font-weight: 500;color: #FFFFFF;padding-top: 30rpx;padding-bottom: 30rpx;"><!-- 标题，下拉框 -->
					<view style="overflow: hidden;"><!-- 使得标题，下拉框水平 -->
						
						<view style="float: left;padding-left: 60rpx;height: 60rpx;">
							<text>上门维修</text>
						</view>
						
						<view style="float: right;padding-right: 60rpx;height: 60rpx;padding-top: 10rpx;">
							<text class="lg text-gray" :class="'cuIcon-unfold'" id="unfold2"@tap="unfold2()"></text>
						</view>
						
						<view style="clear: both;"></view>
						
					</view>
				</view>
				
				<!-- 下拉框显示的内容 -->
				<view id="consent2" style="display:none;" >
					<view style="padding-top: 30rpx;padding-bottom: 10rpx;"><!--  background-color: #6739B6; -->
						
						<view class="cu-list grid col-3">
							<view class="cu-item">
								<navigator url="../release/release"><text>门窗维修</text></navigator>
							</view>
							<view class="cu-item">
								<navigator url="../release/release"><text>厨卫维修</text></navigator>
							</view>
							<view class="cu-item">
								<navigator url="../release/release"><text>管道疏通</text></navigator>
							</view>
							<view class="cu-item">
								<navigator url="../release/release"><text>沙发维修</text></navigator>
							</view>
							<view class="cu-item">
								<navigator url="../release/release"><text>柜子维修</text></navigator>
							</view>
							<view class="cu-item">
								<navigator url="../release/release"><text>床类维修</text></navigator>
							</view>
							<view class="cu-item">
								<navigator url="../release/release"><text>桌子维修</text></navigator>
							</view>
							<view class="cu-item">
								<navigator url="../release/release"><text>空调维修</text></navigator>
							</view>
							<view class="cu-item">
								<navigator url="../release/release"><text>洗衣机维修</text></navigator>
							</view>
						</view>
						
					</view>
				</view><!-- 下拉框显示的内容 -->
				
			</view><!-- 第三个服务 -->
			
			<view style="height: 10rpx;"></view><!-- 每个服务的间隔 -->
			
			<view style="background-color: #8799A3;"><!-- 第三个服务 -->
				<view style="font-size: 40rpx;font-weight: 500;color: #FFFFFF;padding-top: 30rpx;padding-bottom: 30rpx;"><!-- 标题，下拉框 -->
					<view style="overflow: hidden;"><!-- 使得标题，下拉框水平 -->
						
						<view style="float: left;padding-left: 60rpx;height: 60rpx;">
							<text>清洗保洁</text>
						</view>
						
						<view style="float: right;padding-right: 60rpx;height: 60rpx;">
							<text class="lg text-gray" :class="'cuIcon-unfold'" id="unfold3"@tap="unfold3()"></text>
						</view>
						
						<view style="clear: both;"></view>
						
					</view>
				</view>
				
				<!-- 下拉框显示的内容 -->
				<view id="consent3" style="display:none;" >
					<view style="padding-top: 30rpx;padding-bottom: 10rpx; "><!-- background-color: #6739B6; -->
						
						<view class="cu-list grid col-3">
							<view class="cu-item">
								<navigator url="../release/release"><text>油烟机清洗</text></navigator>
							</view>
							<view class="cu-item">
								<navigator url="../release/release"><text>空调清洗</text></navigator>
							</view>
							<view class="cu-item">
								<navigator url="../release/release"><text>洗衣机清洗</text></navigator>
							</view>
							<view class="cu-item">
								<navigator url="../release/release"><text>家庭清洗</text></navigator>
							</view>
							<view class="cu-item">
								<navigator url="../release/release"><text>热水机清洗</text></navigator>
							</view>
							<view class="cu-item">
								<navigator url="../release/release"><text>冰箱清洗</text></navigator>
							</view>
						</view>
						
					</view>
				</view><!-- 下拉框显示的内容 -->
				
			</view><!-- 第二个服务 -->


		</view><!-- 具体内容包裹 -->
		<view>
			<view class="cu-bar tabbar bg-white shadow foot">
				<view class="action" @click="NavChange" data-cur="home">
					<view class='cuIcon-cu-image'>
						<image :src="'/static/tabbar/basics' + [PageCur=='home'?'_cur':''] + '.png'"></image>
					</view>
					<view :class="PageCur=='home'?'text-green':'text-gray'">首页</view>
				</view>
				<view class="action" @click="NavChange" data-cur="order">
					<view class='cuIcon-cu-image'>
						<image :src="'/static/tabbar/component' + [PageCur == 'order'?'_cur':''] + '.png'"></image>
					</view>
					<view :class="PageCur=='order'?'text-green':'text-gray'">订单</view>
				</view>
				<view class="action" @click="NavChange" data-cur="my">
					<view class='cuIcon-cu-image'>
						<image :src="'/static/tabbar/about' + [PageCur == 'my'?'_cur':''] + '.png'"></image>
					</view>
					<view :class="PageCur=='my'?'text-green':'text-gray'">我的</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				PageCur: 'home'
			}
		},
		methods: {
			unfold1(e){
				/* var unfold1=document.getElementById("unfold1"); */
				/* console.log(e.id.valueOf()); */
				let  consent1=document.getElementById("consent1");
				if(consent1.style.display=="none"){
					consent1.style.display="block";
				}else{
					consent1.style.display="none";
				}
			},
			unfold2(e){
				/* var unfold1=document.getElementById("unfold1"); */
				/* console.log(e.id.valueOf()); */
				let  consent1=document.getElementById("consent2");
				if(consent1.style.display=="none"){
					consent1.style.display="block";
				}else{
					consent1.style.display="none";
				}
			},
			unfold3(e){
				/* var unfold1=document.getElementById("unfold1"); */
				/* console.log(e.id.valueOf()); */
				let  consent1=document.getElementById("consent3");
				if(consent1.style.display=="none"){
					consent1.style.display="block";
				}else{
					consent1.style.display="none";
				}
			},
			NavChange(e) {
				this.PageCur = e.currentTarget.dataset.cur
				uni.navigateTo({
					url: "../" + this.PageCur + "/index"
				})
				this.PageCur = "home"
			}
			
		}
	}
</script>

<style>
	@import url("/colorui/animation.css");
	@import url("/colorui/icon.css");
	@import url("/colorui/main.css");
	.head {
		width: calc();
		/* 		height: 160rpx; */
		background-color: #8799A3;
	}

	.view1 {
		width: 95%;
		padding-top: 50rpx;
		padding-bottom: 40rpx;
		margin: auto;
		/* background-color: #6739B6; */
	}

	.input_search_service {
		width: 100%;
		height: 60rpx;
		padding: 15rpx;
		border: 2rpx solid #1CBBB4;
	}

	.btn_search_service {
		width: 160rpx;
		height: 60rpx;
		background-color: #1CBBB4;
		color: #FFFFFF;
	}
</style>
