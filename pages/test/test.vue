<template>
	<view>
		<cu-custom bgColor="bg-gradual-pink" :isBack="true">
			<block slot="backText">返回</block>
			<block slot="content">待完成订单</block>
		</cu-custom>
		<form>
			<view class="cu-form-group margin-top">
				<view class="title">服务单号:000004</view>
			</view>
			<view class="cu-form-group">
				<view class="title">装修师傅:杜师傅</view>
			</view>
			<view class="cu-form-group">
				<view class="title">联系电话:11**</view>
			</view>
			<view class="cu-form-group">
				<view class="title">您的出价:12元</view>
			</view>
			<view class="cu-form-group">
				<view class="title">上门地址:吉*大学</view>
			</view>
			<view class="cu-form-group align-start">
				<view class="title">更多信息</view>
				<textarea maxlength="-1" :disabled="modalName!=null"  placeholder="具体要求:修理洗衣机"></textarea>
			</view>
		</form>
	</view>
</template>

<script>
</script>

<style>
	@import url("/colorui/animation.css");
	@import url("/colorui/icon.css");
	@import url("/colorui/main.css");
	.cu-form-group .title {
		min-width: calc(4em + 15px);
	}
</style>
