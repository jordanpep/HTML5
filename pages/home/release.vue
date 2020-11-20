<template>
	<view>
		<!-- <cu-custom bgColor="bg-gradual-pink" :isBack="true">
			<block slot="backText">返回</block>
			<block slot="content">发布需求</block>
		</cu-custom> -->
		
		<form>
			<view class="cu-form-group margin-top">
				<view class="title">{{serviceType}}<text style="color: #DD514C;">{{serviceItemName}}</text></view>

			</view>

			<view class="cu-form-group align-start">
				<view class="title">{{serviceContent}}</view>

				<textarea maxlength="-1" :disabled="modalName!=null" @input="textareaBInput" :placeholder="serviceContentHint"></textarea>

			</view>

			<view class="cu-form-group">
				<view class="title">{{recommendPrice}}<text style="color: #DD514C;">{{recommendPriceMin}} - {{recommendPriceMax}} 元</text></view>

			</view>
			<view class="cu-form-group">
				<view class="title">{{givePrice}}</view>
				<input :placeholder="givePriceHint" name="input"></input>
			</view>
			<view class="cu-form-group">
				<view class="title">{{homeAdrress}}</view>
				<input :placeholder="homeAdrressHint" name="input"></input>
				<text class='cuIcon-locationfill text-orange'></text>
			</view>

			<view class="cu-form-group">
				<view class="title">{{phoneNumber}}</view>
				<input :placeholder="phoneNumberHint" name="input"></input>
				<view class="cu-capsule radius">
					<view class='cu-tag bg-blue '>
						+86
					</view>
					<view class="cu-tag line-blue">
						中国大陆
					</view>
				</view>
			</view>

			<view class="cu-form-group">
				<view class="title">{{serviceDate}}</view>
				<picker mode="date" :value="date" start="2020-09-01" end="2021-09-01" @change="DateChange">
					<view class="picker">
						{{date}}
					</view>
				</picker>
			</view>
			
			<view class="padding flex flex-direction">
				<button class="cu-btn bg-cyan lg">{{btnPayAndRelease}}</button>
			</view>
			
		</form>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				/* 页面文字信息 */
				serviceType:"服务类型：",
				serviceContent:"服务内容：",
				serviceContentHint:"请输入详细服务内容",
				recommendPrice:"推荐价格：",
				givePrice:"自己出价：",
				givePriceHint:"自己期望价格（元）",
				homeAdrress:"住址",
				homeAdrressHint:"需要服务的地址",
				phoneNumber:"手机号码：",
				phoneNumberHint:"电话号码",
				serviceDate:"希望服务的日期：",
				btnPayAndRelease:"支付并发布",
				/* 页面文字信息 */
				
				
				/* 传参过来的数据加载 */
				serviceItemName:"",
				/* 传参过来的数据加载 */
				
				recommendPriceMin:"100",
				recommendPriceMax:"150",

				date: '2020-09-01',
				modalName: null,
				textareaBValue: '',
				
			};
		},
		methods: {
			onLoad(option){
				this.serviceItemName=JSON.parse(decodeURIComponent(option.serviceItemName));
			},
			
			DateChange(e) {
				this.date = e.detail.value
			},
		
			textareaBInput(e) {
				this.textareaBValue = e.detail.value
			}
		}
	}
</script>

<style>
	.cu-form-group .title {
		min-width: calc(4em + 15px);
	}
</style>
