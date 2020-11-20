<template>
	<view>
		协议内容
		balabala
		balabala
		balabala
		balabala
		balabala
		balabala
		balabala
		balabala
		balabala
		balabala
		balabala
		balabala
		balabala
		balabala
		balabala
		balabala
		balabala
		balabala
		balabala
		balabala
		balabala
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
		},
		onLoad(option) {
			this.userdata = JSON.parse(decodeURIComponent(option.userdata))
		}
	}
</script>

<style>
</style>
