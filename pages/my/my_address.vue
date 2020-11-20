<template>
	<view class="">
		<view class="cu-list menu">
			<view class="cu-item flex flex-wrap" v-for="item in userdata.addressList">
				<view class="basis-90 flex flex-wrap margin-top align-center margin-bottom">
					<text class="basis-xs">{{item.name}}</text>
					<text class="basis-xl text-grey text-sm">{{item.phone}}</text>
					<view>
						{{item.address}}{{item.addressDetail}}
						<text class="cu-tag margin-left line-orange" v-show="item.defaultAddress">默认</text>
					</view>
				</view>
				<view class="margin-top text-gray" @click="">编辑</view>
			</view>
		</view>
		<view class="padding flex flex-direction">
			<button class="cu-btn bg-green lg"><text class="cuIcon-add"></text>添加新地址</button>
		</view>
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
					"phone": 12345678901,
					"defaultAddress": {
						"address": "中国吉林省长春市朝阳区前进大街2699号吉林大学前卫南区",
						"addressName": "北苑一公寓",
						"addressDetail": "北苑一公寓"
					},
					"addressList": [
						{
							"name": "张三",
							"phone": 12345678901,
							"sex": "男",
							"address": "中国吉林省长春市朝阳区前进大街2699号吉林大学前卫南区",
							"addressName": "北苑一公寓",
							"addressDetail": "北苑一公寓",
							"defaultAddress": true
						},
						{
							"name": "李四",
							"phone": 312467381283,
							"sex": "女",
							"address": "北京天安门",
							"addressName": "城楼上",
							"addressDetail": "城楼上",
							"defaultAddress": false
						}
					]
				}	
			}
		},
		onLoad(option) {
			this.userdata = JSON.parse(decodeURIComponent(option.userdata))
		}
	}
</script>

<style>
	.basis-90 {
		flex-basis: 90%;
	}
	.margin-bottom {
		margin-bottom: 30upx;
	}
</style>
