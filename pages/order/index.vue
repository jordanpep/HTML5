<template>
	<view>
		<scroll-view scroll-x class="bg-white nav">
			<view class="flex text-center">
				<view class="cu-item flex-sub" :class="index==TabCur?'text-orange cur':''" v-for="(item,index) in 3" :key="index" @tap="tabSelect" :data-id="index">
					<view></view>
					<view @tap="change(index)" :class="{btna:btnnum == index}">{{Tablist[index]}}</view>
				</view>
			</view>
		</scroll-view>
		
		<view class="end-cont" :class="{dis:btnnum == 0}">
		 　　<section class="mt_like">
		            <ul bailist-style:none>	               
		                <li>
		                    <a class="clearfix">
		                        <image src="/static/pic/dsf.jpg">
		                        <view class="info">
		                            <p class="name">洗衣机修理</p>
		                            <p class="desc">杜师傅</p>
									<p class="more">
										<navigator url="../test/test" hover-class="navigator-hover">
											<view>详情</view>
										</navigator>
									</p>													
		                            <p class="price">
		                                <span class="now">12元</span>
		                                <span class="old">门市价:18元</span>
		                                <span class="dis">当前据您2.2km</span>
		                            </p>
		                        </view>
		                    </a>
		                </li>
		                <li>
		                    <a class="clearfix">
		                        <image src="/static/pic/hsf.png" alt="">
		                        <view class="info">
		                            <p class="name">下水道清理</p>
		                            <p class="desc">何师傅</p>
									<p class="more">
										<navigator url="../test/test" hover-class="navigator-hover">
											<view>详情</view>
										</navigator>
									</p>
		                            <p class="price">
		                                <span class="now">10元</span>
		                                <span class="old">门市价:18元</span>
		                                <span class="dis">当前据您23.1km</span>
		                            </p>
		                        </view>
		                    </a>
		                </li>
					</ul>
		        </section>
		</view>
		<view class="end-cont" :class="{dis:btnnum == 1}">
			<section class="mt_like">
			            <ul bailist-style:none>	               
			                <li>
			                    <a class="clearfix">
			                        <image src="/static/pic/....jpg">
			                        <view class="info">
			                            <p class="name">收破烂</p>
										<p class="desc"></p>
										<p class="more">
											<navigator url="../test-1/test-1" hover-class="navigator-hover">
												<view>详情</view>
											</navigator>
										</p>
										
			                            <p class="price">
			                                <span class="now">您的出价:100元</span>
			                                <span class="old"><br>门市价:118元</span>
			                                <span class="dis">您附近有6位专业师傅,请等待接单</span>
			                            </p>
			                        </view>
			                    </a>
			                </li>
			                <li>
			                    <a class="clearfix">
			                        <image src="/static/pic/baoan.jpg" alt="">
			                        <view class="info">
			                            <p class="name">擦玻璃</p>
										<p class="desc"></p>
										<p class="more">
											<navigator url="../test-1/test-1" hover-class="navigator-hover">
												<view>详情</view>
											</navigator>
										</p>
			                            <p class="price">
			                                <span class="now">您的出价:110元</span>
			                                <span class="old"><br>门市价:118元</span>
			                                <span class="dis">您附近有2位专业师傅,请等待接单</span>
			                            </p>
			                        </view>
			                    </a>
			                </li>
							<li>
							    <a class="clearfix">
							        <image src="/static/pic/cxk.jpg" alt="">
							        <view class="info">
							            <p class="name">守望先锋半藏教学</p>
										<p class="desc"></p>
										<p class="more">
											<navigator url="../test-1/test-1" hover-class="navigator-hover">
												<view>详情</view>
											</navigator>
										</p>
							            <p class="price">
							                <span class="now">您的出价:10元</span>
							                <span class="old"><br>门市价:暂无消息</span>
							                <span class="dis">您附近有0位专业师傅,请再等等吧</span>
							            </p>
							        </view>
							    </a>
							</li>
						</ul>
			        </section>
			</view>
			
		<view class="end-cont" :class="{dis:btnnum == 2}">
		  　<section class="mt_like">
			            <ul bailist-style:none>	               
			                <li>
			                    <a class="clearfix">
			                        <image src="/static/pic/cat.jpg">
			                        <view class="info">
			                            <p class="name">遛猫</p>
										<p class="desc">杜师傅</p>
										<p class="more">
											<navigator url="../test-2/test-2" hover-class="navigator-hover">
												<view>详情</view>
											</navigator>
										</p>
			                            <p class="price">
			                                <span class="now">交易价:100元</span>
			                                <span class="old"></span>
			                                <span class="dis"></span>
			                            </p>
			                        </view>
			                    </a>
			                </li>
			                <li>
			                   <a class="clearfix">
			                       <image src="/static/pic/mask.jpg">
			                       <view class="info">
			                            <p class="name">舞蹈教学</p>
										<p class="desc">杜师傅</p>
										<p class="more">
											<navigator url="../test-2/test-2" hover-class="navigator-hover">
												<view>详情</view>
											</navigator>
										</p>
			                           <p class="price">
			                               <span class="now">交易价:10元</span>
			                               <span class="old"></span>
			                               <span class="dis"></span>
			                           </p>
			                       </view>
			                   </a>
			                </li>
							<li>
							    <a class="clearfix">
							        <image src="/static/pic/Christmax.jpg">
							        <view class="info">
							            <p class="name">充当圣诞树</p>
							    		<p class="desc">杜师傅</p>
										<p class="more">
											<navigator url="../test-2/test-2" hover-class="navigator-hover">
												<view>详情</view>
											</navigator>
										</p>
							            <p class="price">
							                <span class="now">交易价:1元</span>
							                <span class="old"></span>
							                <span class="dis"></span>
							            </p>
							        </view>
							    </a>
							</li>
						</ul>
			        </section>
		</view>
		<!-- <view>
			<view class="cu-bar tabbar bg-white shadow foot">
				<view class="action" @click="NavChange" data-cur="home">
					<view class='cuIcon-cu-image'>
						<image :src="'/static/tabbar/basics' + [PageCur=='home'?'_cur':''] + '.png'"></image>
					</view>
					<view :class="PageCur=='home'?'text-green':'text-gray'">首页</view>
				</view>
				<view class="action" @click="NavChange" data-cur="order">
					<view class='cuIcon-cu-image'>
						<image :src="'/static/tabbar/component' + [PageCur == 'order'?'_cur':''] + '.png'"></image>
					</view>
					<view :class="PageCur=='order'?'text-green':'text-gray'">订单</view>
				</view>
				<view class="action" @click="NavChange" data-cur="my">
					<view class='cuIcon-cu-image'>
						<image :src="'/static/tabbar/about' + [PageCur == 'my'?'_cur':''] + '.png'"></image>
					</view>
					<view :class="PageCur=='my'?'text-green':'text-gray'">我的</view>
				</view>
			</view>
		</view> -->
	</view>
	
</template>

<script>
	export default {
		data() {
			return {
				btnnum: 0,
				TabCur: 0,
				PageCur: "order",
				Tablist:['待服务','待接单','已完成'],
				scrollLeft: 0
			};
		},
		methods: {
			tabSelect(e) {
				this.TabCur = e.currentTarget.dataset.id;
				this.scrollLeft = (e.currentTarget.dataset.id - 1) * 60
			},
			change(e) {
			    this.btnnum = e
			    console.log(this.btnnum)
			},
			NavChange(e) {
				this.PageCur = e.currentTarget.dataset.cur
				uni.navigateTo({
					url: "../" + this.PageCur + "/index"
				})
			}
		},
		onLoad(option) { //option为object类型，会序列化上个页面传递的参数
		        console.log(option.id); //打印出上个页面传递的参数。
		        console.log(option.name); //打印出上个页面传递的参数。
		}
	}

</script>

<style>
	.end-title{
	    display: flex;
	}
	.end-title view{
	    flex-grow: 1;
	    text-align: center;
	}
	.end-cont{
	    display: none;
	    background: #C8C7CC;
	}
	.dis{
	    display: block;
	}    
	.btna{
	    color: #000000;
	    /* background: #00A0FF; */
	}
	ul{list-style: none;}
	.mt_like{
	    box-shadow: 0 0 1px #ccc;
	    margin-top:10px;
	    min-height: 500px;
	    padding: 0 10px;
	    background: #fff;
	}
	.mt_like h3{
	    padding: 10px 0;
	    font-size: 16px;
	    line-height: 1;
	    font-weight: normal;
	    color: #666;
	}
	.mt_like ul li{
	    padding: 10px 0;
	    border-top: 1px solid #eee;
	}
	.mt_like ul li a{
	    display: block;
	    color: #666;
	}
	.mt_like ul li a image{
	    width: 90px;
	    height: 90px;
	    float: left;
	}
	.mt_like ul li a .info{
	    overflow: hidden;
	    line-height: 1;
	    padding-left:10px;
	}
	.mt_like ul li a .info .more{
	    float: right;
	    margin-top: -60px;
		margin-right: 10px;
	    font-size: 15px;
	}
	.mt_like ul li a .info .name{
	    font-size: 16px;
	    padding-bottom: 10px;
	    padding-top: 4px;
	    color: #444;
	}
	.mt_like ul li a .info .desc{
	    font-size: 12px;
	    padding-bottom: 10px;
	    line-height: 16px;
	    height: 42px;
	    width: 100%;
	    overflow: hidden;
	}
	.mt_like ul li a .info .now{
	    color: #68dbce;
	    font-size: 16px;
	    font-weight: bold;
	}
	.mt_like ul li a .info .old{
	    font-size: 12px;
	}
	.mt_like ul li a .info .dis{
	    float: right;
	    margin-top: 4px;
	    font-size: 12px;
	}
	
</style>

