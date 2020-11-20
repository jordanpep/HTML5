<template>

	<view>

		<!-- 头部搜索，定位栏 -->
		<view class="head bg-gradual-orange">
			<view class="view1">
				<!-- 包裹 头部搜索，定位栏 -->
				<view style=" float: left;height: 60rpx;width:100rpx;text-align: center;overflow: hidden;">
					<view style="height: 30rpx;">
						<text class="lg text-red" :class="'cuIcon-locationfill'" id="location"></text><!-- location为用户位置定位 -->
					</view>
					<view style="font-size: 20rpx;height: 30rpx;">
						<text style="font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">{{userLocation}}</text>
					</view>
				</view>

				<view style="width: 450rpx; float: left;padding-left: 15rpx;padding-right: 5rpx;">
					<input :placeholder="searchHint" class="input_search_service" type="text" />
				</view>

				<button class="cu-btn  lg btn_search_service" style="float: left;">{{btnSearch}}</button>
				<view style="clear: both;"></view>
			</view>
		</view>

		<view style="height: 30rpx;background-color: #E7EBED"></view><!-- 中间隔断 -->

		<!-- 具体内容部分，一个分类的列表 background-color: #886666;-->
		<view ><!-- style="padding-top: 30rpx;padding-bottom: 20rpx;" --><!-- 包裹每个服务 -->
			<view v-for="(typeItem,index) in ServiceType" :key="index"><!-- 单个服务模块 -->
				
				<view class="bg-gradual-blue">
					<!-- 第一个服务 -->
					<view style="font-size: 40rpx;font-weight: 500;color: #FFFFFF;padding-top: 30rpx;padding-bottom: 30rpx;">
						<!-- 标题，下拉框 -->
						<view style="overflow: hidden;">
							<!-- 使得标题，下拉框水平 -->

							<view style="float: left;padding-left: 60rpx;height: 60rpx;">
								<text>{{typeItem.serviceTypeName}}</text>
							</view>

							<view style="float: right;padding-right: 60rpx;height: 60rpx;padding-top: 10rpx;">
								<text class="lg text-gray" :class="'cuIcon-'+typeItem.foldType" @tap="Unfold(typeItem)"></text>
							</view>

							<view style="clear: both;"></view>

						</view>
					</view>

					<!-- 下拉框显示的内容 -->
					<view  :class="typeItem.isShow?'':'service_type_noShow'">
						<view style="padding-bottom: 2rpx;background-color: #C0C0C0; " class="shadow">
							<!-- padding-top: 30rpx;background-color: #6739B6; -->

							<view class="cu-list grid col-3">
								<view class="cu-item" v-for="(item,itemIndex) in typeItem.serviceItem" :key="itemIndex"><!--每个服务大类下的服务小类 -->
									<text @tap="LinkRelease(item.serviceItemName)">{{item.serviceItemName}}</text>
								</view>
							</view>

						</view>
					</view><!-- 下拉框显示的内容 -->

				</view><!-- 第一个服务 -->

				<view style="height: 2rpx;"></view><!-- 每个服务的间隔 -->
				
			</view><!-- 单个服务模块 -->
			
		</view><!-- 具体内容包裹 -->

	</view>
</template>

<script>
	export default {
		data() {
			return {
				
				/* 按钮，默认提示字等固定文字 */
				searchHint:"查询服务",
				btnSearch:"搜索",
				/* 按钮，默认提示字等固定文字 */
				
				/* 下面都是可能会变化的量 */
				userLocation:"长春",
				ServiceType: [{
					isShow:"true",
					foldType:"fold",
					serviceTypeName: "上门安装",
					serviceItem: [{
						serviceItemName: "宜家组装"
					}, {
						serviceItemName: "厨卫组装"
					}, {
						serviceItemName: "灯具组装"
					}, {
						serviceItemName: "柜类组装"
					}, {
						serviceItemName: "床类组装"
					}, {
						serviceItemName: "座椅组装"
					}]
				}, {
					isShow:"true",
					foldType:"fold",
					serviceTypeName: "上门维修",
					serviceItem: [{
						serviceItemName: "宜家维修"
					}, {
						serviceItemName: "厨卫维修"
					}, {
						serviceItemName: "管道疏通"
					}, {
						serviceItemName: "沙发维修"
					}, {
						serviceItemName: "柜子维修"
					}, {
						serviceItemName: "床类维修"
					}, {
						serviceItemName: "桌子维修"
					}, {
						serviceItemName: "空调维修"
					}, {
						serviceItemName: "洗衣机维修"
					}]
				}, {
					isShow:"true",
					foldType:"fold",
					serviceTypeName: "清洗保洁",
					serviceItem: [{
						serviceItemName: "油烟机清洗"
					}, {
						serviceItemName: "热水器清洗"
					}, {
						serviceItemName: "洗衣机清洗"
					}, {
						serviceItemName: "家庭清洗"
					}, {
						serviceItemName: "热水机清洗"
					}, {
						serviceItemName: "冰箱清洗"
					}]
				}],

			/* 	PageCur: 'home' */
			}
		},
		methods: {
			Unfold(e){
				if(e.isShow){
					e.isShow=false;
					e.foldType="unfold"
				}else{
					e.isShow=true;
					e.foldType="fold"
				}
			},
			
			LinkRelease(e){
				/* console.log(e) */
				uni.navigateTo({
					url:"./release?serviceItemName="+encodeURIComponent(JSON.stringify(e))
				})
			},
			
			/* NavChange(e) {
				this.PageCur = e.currentTarget.dataset.cur
				uni.navigateTo({
					url: "../" + this.PageCur + "/index"
				})
				this.PageCur = "home"
			} */

		}
	}
</script>

<style>
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
	
	.service_type_noShow{
		display: none;
	}
	
</style>
