<template>
	<view class="padding">
		<form>
			<view class="cu-form-group margin-top">
				<view class="basis-xs margin-xs">姓名</view>
				<input :value="userdata.name" name="input" @input="nameChange"></input>
			</view>
			<view class="cu-form-group">
				<view class="basis-xs margin-xs">性别</view>
				<picker class="flex" @change="sexChange" :range="sexPicker">
					<view class="picker">
						{{sexIndex>-1?sexPicker[sexIndex]:"请选择性别"}}
					</view>
				</picker>
			</view>
			<!-- <view class="cu-form-group">
				<view class="basis-xs margin-xs">地址</view>
				<input :value="userdata.address" name="input" @click="chooseLocation"></input>
				<text class='cuIcon-locationfill text-orange'></text>
			</view>
			<view class="cu-form-group">
				<view class="basis-xs margin-xs">门牌</view>
				<input :value="userdata.addressDetail" name="input"></input>
			</view> -->
			<view class="cu-form-group">
				<view class="basis-xs margin-xs">手机</view>
				<input :value="userdata.phone" name="input" @input="phoneChange"></input>
			</view>
			<!-- <view class="cu-form-group">
				<view class="title">验证码</view>
				<input placeholder="输入框带个按钮" name="input"></input>
				<button class='cu-btn bg-green shadow'>验证码</button>
			</view> -->
			<view class="padding flex flex-direction">
				<button class="cu-btn bg-blue lg" @click="saveChange()">保存</button>
			</view>
		</form>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				userdata: {
					"nickname": "SAGIRI",
					"userId": 0,
					"name": "giao哥",
					"sex": "女",
					"address": "中国吉林省长春市朝阳区前进大街2699号吉林大学前卫南区",
					"addressDetail": "北苑一公寓",
					"phone": 12345678901
				},
				"sexIndex": -1,
				"sexPicker": ["男", "女"],
				"source": "personal_info"
			}
		},
		onLoad(option) {
			this.userdata = JSON.parse(decodeURIComponent(option.userdata))
			this.setSex(this.userdata.sex)
		},
		methods: {
			setSex(sex) {
				if(sex == "男") {
					this.sexIndex = 0
				} else if(sex == "女") {
					this.sexIndex = 1
				} else {
					this.sexIndex = -1
				}
			},
			nameChange(e) {
				this.userdata.name = e.detail.value
			},
			sexChange(e) {
				this.sexIndex = e.detail.value
				this.userdata.sex = this.sexPicker[this.sexIndex]
			},
			chooseLocation() {
				uni.chooseLocation({
					success: (data)=> {
						// this.addressData.addressName = data.name;
						this.userdata.address = data.address;
					}
				})
			},
			addressChange(e) {
				this.userdata.address = e.detail.value
			},
			phoneChange(e) {
				this.userdata.phone = e.detail.value
			},
			saveChange() {
				uni.navigateTo({
					url: "./personal_info?userdata=" + encodeURIComponent(JSON.stringify(this.userdata))
				})
			}
		}
	}
</script>

<style>
</style>
