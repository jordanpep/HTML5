<template>
	<view>
		<form>
			<view class="cu-form-group">
				<view class="title">手机</view>
				<input name="input" placeholder="请输入手机号" @input="phoneChange"></input>
				<navigator>获取验证码</navigator>
			</view>
			<view class="cu-form-group">
				<view class="title">验证码</view>
				<input name="input" placeholder="请输入验证码" @input="phoneChange"></input>
			</view>
			<view class="padding flex flex-direction">
				<button class="cu-btn bg-green lg" @click="saveChange()">确定</button>
			</view>
		</form>
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
					"address": "中国吉林省长春市朝阳区前进大街2699号吉林大学前卫南区",
					"phone": 12345678901
				}
			}
		}
	}
</script>

<style>
</style>
