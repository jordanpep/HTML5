<template>
	<view>
		
			<view>
				<view class="cu-list menu margin-top">
					<view class="cu-item arrow">
						<button class="content flex" hover-class="none" @click="edit_info" open-type="redirect">
							<text class="cuIcon-edit text-orange"></text>
							<text class="text-grey">个人信息修改</text>
						</button>
					</view>
					<view class="cu-item arrow">
						<button class="content flex" hover-class="none" @click="cancellation" open-type="redirect">
							<text class="cuIcon-warn text-orange"></text>
							<text class="text-grey">注销账户</text>
						</button>
					</view>
					<view class="cu-item arrow margin-top">
						<button class="content flex" hover-class="none" @click="about">
							<text class="cuIcon-question text-orange"></text>
							<text class="text-grey">关于</text>
						</button>
					</view>
					<view class="cu-item arrow">
						<button class="content flex" hover-class="none" @click="service_agreement" open-type="redirect">
							<text class="cuIcon-read text-orange"></text>
							<text class="text-grey">服务协议</text>
						</button>
					</view>
					<view class="cu-item arrow margin-top">
						<button class="content flex" hover-class="none" @click="" open-type="redirect">
							<text class="cuIcon-delete text-orange"></text>
							<text class="text-grey">清除缓存</text>
						</button>
					</view>
					<view class="cu-item arrow">
						<button class="content flex" hover-class="none" @click="show_version" open-type="redirect">
							<text class="cuIcon-info text-orange"></text>
							<text class="text-grey">当前版本</text>
						</button>
					</view>
					<view class="padding flex flex-direction">
						<button class="cu-btn bg-blue lg" @tap="log_out">退出登录</button>
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
					"nickname": "",
					"userId": 0,
					"name": "",
					"sex": "",
					"address": "",
					"phone": 0
				},
				version: "v0.0.1"
			}
		},
		onLoad(option) {
			this.userdata = JSON.parse(decodeURIComponent(option.userdata))
		},
		methods: {
			edit_info() {
				uni.navigateTo({
					url: "./edit_info?userdata=" + encodeURIComponent(JSON.stringify(this.userdata)),
				})
			},
			cancellation() {
				uni.navigateTo({
					url: "./cancellation?userdata=" + encodeURIComponent(JSON.stringify(this.userdata)),
				})
			},
			about() {
				uni.navigateTo({
					url: "./about?userdata=" + encodeURIComponent(JSON.stringify(this.userdata)),
				})
			},
			service_agreement() {
				uni.navigateTo({
					url: "./service_agreement?userdata=" + encodeURIComponent(JSON.stringify(this.userdata)),
				})
			},
			show_version() {
				uni.showToast({
				    title: '当前版本：' + this.version,
					icon: "none"
				});
			},
			log_out() {
				uni.showModal({
				    title: '退出登录',
				    content: '确定要退出登录吗？',
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
</style>
