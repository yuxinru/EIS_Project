<template>
	<view>
		<view class="question">
			<swiper class="swiper" indicator-dots="true" >
				<swiper-item>
					<view class="question">
					   <text>选择题一：{{x1.Xzt[0]['stnr']}}</text>
					</view>
					<uni-xzt :xx1="x1.Xzt[0]['xx1']"
							  :xx2="x1.Xzt[0]['xx1']"
							  :xx3="x1.Xzt[0]['xx1']"  @click="onClick"
							  ></uni-xzt>
				</swiper-item>
				<swiper-item>
					<view class="question">
					   <text>选择题二：{{x1.Xzt[0]['stnr']}}</text>
					</view>
					<uni-xzt :xx1="x1.Xzt[0]['xx1']"
							  :xx2="x1.Xzt[0]['xx1']"
							  :xx3="x1.Xzt[0]['xx1']"  @click="onClick1"
							  ></uni-xzt>
				</swiper-item>
				<swiper-item>
					<view class="question">
					   <text>选择题三：{{x1.Xzt[0]['stnr']}}</text>
					</view>
					<uni-xzt :xx1="x1.Xzt[0]['xx1']"
							  :xx2="x1.Xzt[0]['xx1']"
							  :xx3="x1.Xzt[0]['xx1']"  @click="onClick2"
							  ></uni-xzt>
				</swiper-item>
				<swiper-item>
					<view class="question">
					   <text>选择题四：{{x1.Xzt[0]['stnr']}}</text>
					</view>
					<uni-xzt :xx1="x1.Xzt[0]['xx1']"
							  :xx2="x1.Xzt[0]['xx1']"
							  :xx3="x1.Xzt[0]['xx1']"  @click="onClick3"
							  ></uni-xzt>
				</swiper-item>
				<swiper-item>
					<view class="question">
					   <text>问答题一：{{x1.Xzt[0]['stnr']}}</text>
					</view>
					<view>
						<textarea placeholder="请在这里输入你的答案..." v-model="a5" class="wdt-module"></textarea>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="question">
					   <text>问答题二：{{x1.Xzt[0]['stnr']}}</text>
					</view>
					<view>
						<textarea placeholder="请在这里输入你的答案..." v-model="a5" class="wdt-module"></textarea>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="question">
					   <text>问答题三：{{x1.Xzt[0]['stnr']}}</text>
					</view>
					<view>
						<textarea placeholder="请在这里输入你的答案..." v-model="a5" class="wdt-module"></textarea>
					</view>
				</swiper-item>
			</swiper>
			<view class="bottom">
				<button type="primary" @click="submit">提交</button>
				<text>[提交后不可再修改]</text>
			</view>
		</view>
	</view>
</template>

<script>
	//import uniList from '@/components/uni-list/uni-list.vue'
	//import uniListItem from '@/components/uni-list-item/uni-list-item.vue'
    import uniNoticeBar from "@/components/uni-notice-bar/uni-notice-bar.vue"
    import uniXzt from "../../components/xzt/xzt.vue"

	export default {
		components: {uniNoticeBar,uniXzt},
		data() {
			return {
				xqid:-1,
				list:[],
				currentInfo:[],
				x1:[],
				x2:[],
				x3:[],
				x4:[],
				x5:[],
				x6:[],
				x7:[],
				a1:'',a2:'',a3:'',a4:'',
				a5:'',a6:'',a7:''
			}
		},
		onLoad:function(option){
			this.xqid = option.id
		},
		onShow:function(){
			/*
			uni.request({
				url:"http://47.103.7.215:8080/Entity/U19e975fabb160/ExamSystem/Scdsj/?Scdsj.xqid="+this.xqid,
			    success:(res)=>{
					this.list = res.data;
					this.currentInfo=this.list.Scdsj[2];  //随机选取某个数字，即随机试卷
					uni.request({
						url:"http://47.103.7.215:8080/Entity/U19e975fabb160/ExamSystem/Xzt/"+this.currentInfo['bh1'],
						success:(res)=>{
							this.x1 = res.data
						}
					})
					uni.request({
						url:"http://47.103.7.215:8080/Entity/U19e975fabb160/ExamSystem/Xzt/"+this.currentInfo['bh2'],
						success:(res)=>{
							this.x2 = res.data
						}
					})
					uni.request({
						url:"http://47.103.7.215:8080/Entity/U19e975fabb160/ExamSystem/Xzt/"+this.currentInfo['bh3'],
						success:(res)=>{
							this.x3 = res.data
						}
					})
					uni.request({
						url:"http://47.103.7.215:8080/Entity/U19e975fabb160/ExamSystem/Xzt/"+this.currentInfo['bh4'],
						success:(res)=>{
							this.x4 = res.data
						}
					})
					uni.request({
						url:"http://47.103.7.215:8080/Entity/U19e975fabb160/ExamSystem/Xzt/"+this.currentInfo['bh5'],
						success:(res)=>{
							this.x5 = res.data
						}
					})
					uni.request({
						url:"http://47.103.7.215:8080/Entity/U19e975fabb160/ExamSystem/Xzt/"+this.currentInfo['bh6'],
						success:(res)=>{
							this.x6 = res.data
						}
					})
					uni.request({
						url:"http://47.103.7.215:8080/Entity/U19e975fabb160/ExamSystem/Xzt/"+this.currentInfo['bh7'],
						success:(res)=>{
							this.x7 = res.data
						}
					})		
			})*/
			this.x1={
					"Xzt":[
						{"stnr":"the question",
						"xx1":"choice1hhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhchoice",
						"xx2":"choice2",
						"xx3":"choice3"}
						]
				
			}
		},
		methods: {
			radioChange:function(evt){
				this.a1 = evt.target.value;
				console.log(this.a1)
			},
			onClick:function(e){
				this.a1 = e.result;
				//console.log(this.a1)
			},
			onClick1:function(e){
				this.a2 = e.result;
				//console.log(this.a1)
			},
			onClick2:function(e){
				this.a3 = e.result;
				//console.log(this.a1)
			},
			onClick3:function(e){
				this.a4 = e.result;
				//console.log(this.a1)
			},
			submit:function(){
				//console.log(this.a5)
			}
		}
	}
</script>
<style>
	.swiper{
		height:1000upx
	}
	.question{
		margin-bottom: 20upx;
	}
	.wdt-module{
		height: 500upx;
		font-size: 34upx;
		line-height: 50upx;
		width: 100%;
		box-sizing: border-box;
		margin-left: 20upx;
		margin-right: 20upx;
		margin-bottom: 10upx;
		background-color:#F0F0F0
	}
	.bottom{
		text-align: center;
	}
</style>
