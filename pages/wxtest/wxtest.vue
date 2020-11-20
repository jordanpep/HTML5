<template>
	<view>
		<button @tap="loginByWeixin">test</button>
	</view>
</template>

<script>
	let weixinAuthService
	export default {
	  data() {
	    return {
	      hasWeixinAuth: false
	    }
	  },
	  onLoad() {
	    // #ifdef APP-PLUS
	    plus.oauth.getServices((services) => {
	      weixinAuthService = services.find((service) => {
	        return service.id === 'weixin'
	      })
	      if (weixinAuthService) {
	        this.hasWeixinAuth = true
	      }
	    });
	    // #endif
	  },
	  methods: {
	    getWeixinCode() {
	      return new Promise((resolve, reject) => {
	        // #ifdef MP-WEIXIN
	        uni.login({
	          provider: 'weixin',
	          success(res) {
	            resolve(res.code)
				console.log(res)
	          },
	          fail(err) {
	            reject(new Error('微信登录失败1'))
	          }
	        })
	        // #endif
	        // #ifdef APP-PLUS
	        weixinAuthService.authorize(function(res) {
	          resolve(res.code)
	        }, function(err) {
	          console.log(err)
	          reject(new Error('微信登录失败'))
	        });
	        // #endif
	      })
	    },
	    loginByWeixin() {
	      this.getWeixinCode().then((code) => {
	        return uniCloud.callFunction({
	          name: 'loginByWeixin',
	          params: {
	            code
	          }
	        })
	      }).then((res) => {
	        uni.showModal({
	          showCancel: false,
	          content: JSON.stringify(res.result)
	        })
	        if (res.result.code === 0) {
	          uni.setStorageSync('uniIdToken', res.result.token)
	        }
	      }).catch(() => {
	        uni.showModal({
	          showCancel: false,
	          content: '微信登录失败，请稍后再试2'
	        })
	      })
	    }
	  }
	}
</script>

<style>

</style>
