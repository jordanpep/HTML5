<template>
	<view class="">
		<view class="cu-list menu card-menu margin-top">
			<view class="cu-item">
				<view class="content">
					<text class="cuIcon-people text-grey"></text>
					<text class="text-grey">姓名</text>
					<text class="padding">{{userdata.name}}</text>
				</view>
			</view>
			<view class="cu-item">
				<view class="content">
					<text class="cuIcon-male text-grey"></text>
					<text class="text-grey">性别</text>
					<text class="padding">{{userdata.sex}}</text>
				</view>
			</view>
			<!-- <view class="cu-item">
				<view class="content">
					<view class="content">
						<text class="cuIcon-home text-grey"></text>
						<text class="text-grey">地址</text>
						<view class="padding flex-sub">
							<text>{{userdata.defaultAddress.address}}{{userdata.defaultAddress.addressDetail}}</text>
						</view>
					</view>
				</view>
			</view> -->
			<view class="cu-item">
				<view class="content">
					<text class="cuIcon-phone text-grey"></text>
					<text class="text-grey">电话</text>
					<text class="padding">{{userdata.phone}}</text>
				</view>
			</view>
			<view class="padding flex flex-direction">
				<button class="cu-btn bg-blue lg" @tap="edit_info()">编辑</button>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				userdata: {}	
			}
		},
		onLoad(option) {
			this.userdata = JSON.parse(decodeURIComponent(option.userdata))
		},
		methods: {
			edit_info(){
				uni.navigateTo({
					url: "./edit_info?userdata=" + encodeURIComponent(JSON.stringify(this.userdata)),
				})
			}
		}
	}
</script>

<style>
</style>
