<template>
	<view>
		<view>
			<view class="cu-list menu card-menu margin-top">
				<view class="cu-item">
					<view class="flex padding cu-item">
						<view class="cu-avatar xl round" style="background-image:url(https://ossweb-img.qq.com/images/lol/web201310/skin/big99008.jpg);"></view>
						<text class="padding margin-left text-xl">{{userdata.nickname}}</text>
					</view>
				</view>
				<view class="cu-item arrow">
					<button class="content flex" hover-class="none" @click="personal_info" open-type="redirect">
						<text class="cuIcon-profilefill text-orange"></text>
						<text class="text-grey">个人信息</text>
					</button>
				</view>
				<view class="cu-item arrow">
					<button class="content flex" hover-class="none" @click="my_address" open-type="redirect">
						<text class="cuIcon-homefill text-orange"></text>
						<text class="text-grey">我的地址</text>
					</button>
				</view>
				<view class="cu-item arrow">
					<button class="content flex" hover-class="none" open-type="redirect">
						<text class="cuIcon-rankfill text-orange"></text>
						<text class="text-grey">数据分析</text>
					</button>
				</view>
				<view class="cu-item arrow">
					<button class="content flex" hover-class="none" @click="feedback" open-type="redirect">
						<text class="cuIcon-formfill text-orange"></text>
						<text class="text-grey">意见反馈</text>
					</button>
				</view>
				<view class="cu-item arrow">
					<button class="content flex" hover-class="none" @click="service" open-type="redirect">
						<text class="cuIcon-servicefill text-orange"></text>
						<text class="text-grey">联系客服</text>
					</button>
				</view>
				<view class="cu-item arrow">
					<button class="content flex" hover-class="none" @click="setting" open-type="redirect">
						<text class="cuIcon-settingsfill text-orange"></text>
						<text class="text-grey">设置</text>
					</button>
				</view>
			</view>
			<view class="cu-list menu card-menu margin-top">
				<view class="cu-item arrow">
					<button class="content flex" @click="master_app">
						<text class="cuIcon-btn text-green"></text>
						<text class="text-grey">我是师傅</text>
					</button>
				</view>
			</view>
			<view class="cu-list menu card-menu margin-top">
				<view class="cu-item arrow">
					<button class="content flex" @click="wxtest">
						<text class="cuIcon-btn text-green"></text>
						<text class="text-grey">我是测试</text>
					</button>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				PageCur: "my",
				userdata: {
					"nickname": "SAGIRI",
					"userId": 0,
					"name": "giao哥",
					"sex": "女",
					"phone": 12345678901,
					"defaultAddress": {
						"address": "中国吉林省长春市朝阳区前进大街2699号吉林大学前卫南区",
						"addressName": "北苑一公寓",
						"addressDetail": "北苑一公寓"
					},
					"addressList": [
						{
							"name": "SAGIRI",
							"phone": 12345678901,
							"sex": "男",
							"address": "中国吉林省长春市朝阳区前进大街2699号吉林大学前卫南区",
							"addressName": "北苑一公寓",
							"addressDetail": "北苑一公寓",
							"defaultAddress": true
						},
						{
							"name": "张三",
							"phone": 18203628182,
							"sex": "女",
							"address": "中国吉林省长春市朝阳区前进大街2699号吉林大学前卫南区",
							"addressName": "南苑九公寓",
							"addressDetail": "南苑九公寓",
							"defaultAddress": false
						},
						{
							"name": "李四",
							"phone": 13651235371,
							"sex": "男",
							"address": "北京天安门",
							"addressName": "北京天安门",
							"addressDetail": "城楼上",
							"defaultAddress": false
						},
					]
				}
			}
		},
		onLoad() {
			// data init
		},
		methods: {
			personal_info(){
				uni.navigateTo({
					url: "./personal_info?userdata=" + encodeURIComponent(JSON.stringify(this.userdata)),
				})
			},
			feedback(){
				uni.navigateTo({
					url: "./feed_back?userdata=" + encodeURIComponent(JSON.stringify(this.userdata))
				})
			},
			setting(){
				uni.navigateTo({
					url: "./setting?userdata=" + encodeURIComponent(JSON.stringify(this.userdata))
				})
			},
			my_address(){
				uni.navigateTo({
					url: "./my_address?userdata=" + encodeURIComponent(JSON.stringify(this.userdata))
				})
			},
			service(){
				uni.navigateTo({
					url: "./service?userdata=" + encodeURIComponent(JSON.stringify(this.userdata))
				})
			}
			,wxtest(){
				uni.navigateTo({
					url: "../wxtest/wxtest?userdata=" + encodeURIComponent(JSON.stringify(this.userdata))
				})
			},
			NavChange(e) {
				this.PageCur = e.currentTarget.dataset.cur
				uni.navigateTo({
					url: "../" + this.PageCur + "/index"
				})
			},
			master_app() {
				uni.showModal({
				    title: '我是师傅',
				    content: '确定前往急了吗——师傅端？',
				    success: function (res) {
				        if (res.confirm) {
				            console.log('用户点击确定');
				        } else if (res.cancel) {
				            console.log('用户点击取消');
				        }
				    }
				});
			}
			
		}
	}
</script>

<style>
	.bottom {
		padding-bottom: 0rpx;
		margin-bottom: 0rpx;
	}
	uni-page-head {
		display: none;
	}
</style>
