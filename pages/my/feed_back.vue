<template>
	<view class="padding">
		<form>
			<view class="cu-bar bg-white">
				<view class="action text-left">问题描述</view>
				<view class="action">{{charCount}}/200</view>
			</view>
			<view class="cu-form-group align-start">
				<textarea maxlength="-1" @input="textareaInput" placeholder="请在此输入问题描述"></textarea>
			</view>
			<view class="cu-bar bg-white margin-top">
				<view class="action">图片上传</view>
				<view class="action">{{imgList.length}}/4</view>
			</view>
			<view class="cu-form-group">
				<view class="grid col-4 grid-square flex-sub">
					<view class="bg-img" v-for="(item,index) in imgList" :key="index" @tap="ViewImage" :data-url="imgList[index]">
					 <image :src="imgList[index]" mode="aspectFill"></image>
						<view class="cu-tag bg-red" @tap.stop="DelImg" :data-index="index">
							<text class='cuIcon-close'></text>
						</view>
					</view>
					<view class="solids" @tap="ChooseImage" v-if="imgList.length<4">
						<text class='cuIcon-cameraadd'></text>
					</view>
				</view>
			</view>
			<view class="padding flex flex-direction">
				<button class="cu-btn bg-blue lg" url="./edit_info">提交</button>
			</view>
		</form>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				userdata: {},
				imgList: [],
				index: -1,
				charCount: 0,
				textValue: ""
			}
		},
		onLoad(option) {
			this.userdata = JSON.parse(decodeURIComponent(option.userdata))
		},
		methods: {
			ViewImage(e) {
				uni.previewImage({
					urls: this.imgList,
					current: e.currentTarget.dataset.url
				});
			},
			DelImg(e) {
				uni.showModal({
					title: 'Alert',
					content: '确定删除这张照片吗？',
					cancelText: '取消',
					confirmText: '确定',
					success: res => {
						if (res.confirm) {
							this.imgList.splice(e.currentTarget.dataset.index, 1)
						}
					}
				})
			},
			ChooseImage() {
				uni.chooseImage({
					count: 4, //默认9
					sizeType: ['original', 'compressed'], //可以指定是原图还是压缩图，默认二者都有
					sourceType: ['album'], //从相册选择
					success: (res) => {
						if (this.imgList.length != 0) {
							this.imgList = this.imgList.concat(res.tempFilePaths)
						} else {
							this.imgList = res.tempFilePaths
						}
					}
				});
			},
			textareaInput(e) {
				this.textValue = e.detail.value
				this.charCount = this.textValue.length
			}
		}
	}
</script>

<style>
</style>
