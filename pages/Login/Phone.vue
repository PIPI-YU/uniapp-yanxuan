<template>
  <view id="LoginPhoneContainer">
		<view class="LoginPhoneHead">
      <view class="header">
      		<view class="left">
      			<image src="../../static/images/Worth/home02.png" mode="" @click="goHome"></image>
      		</view>
      		<view class="center">网易严选</view>
      		<view class="right">
      			<image class="fangdajing" src="../../static/images/Worth/search.png" mode="" @click="goSearch"></image>
      			<image class="gouwuche" src="../../static/images/Worth/cart02.png" mode="" @click="goCart"></image>
      		</view>
      </view>
    </view>
		<view class="LoginPhoneContent">
			<view class="top">
				<image src="../../static/images/Personal/yanxuan.png" mode=""></image>
			</view>
			<view class="center">
				<input placeholder="请输入手机号">
				<view class="getCode">
					<input placeholder="请输入短信验证码">
					<view class="Code">获取验证码</view>
				</view>
				<view class="in-forget">
					<view class="new">遇到问题？</view>
					<view class="forget">使用密码验证登录</view>
				</view>
				<view class="loginButton">登录</view>
				<view class="other" @click="goPersonal">
					<span>其他登录方式 ></span>
				</view>
			</view>
		</view>
  </view>
</template>

<script type="text/ecmascript-6">
  export default {
		methods:{
			goHome(){
				uni.switchTab({
					url:"../Home/index"
				})
			},
			goSearch(){
				uni.navigateTo({
					url:"../Search/index"
				})
			},
			goCart(){
				uni.switchTab({
					url:"../Cart/index"
				})
			},
			goPersonal(){
				uni.switchTab({
					url:"../Personal/index"
				})
			}
		}
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
	#LoginPhoneContainer
		width 750upx
		height 1334upx
		box-sizing border-box
		.LoginPhoneHead
			width 750upx
			height 100upx
			position fixed
			left 0
			top 0
			z-index 1
			background #fafafa
			.header
				display flex
				width 700upx
				height 100upx
				line-height 100upx
				margin 0 25upx
				box-sizing border-box
				.left
					width 60upx
					height 60upx
					margin-top 15upx
					image
						width 60upx
						height 60upx
				.center
					height 100upx
					line-height 100upx
					margin 0 135upx 0 215upx
					text-align center
					font-size 36upx
					color #000
				.right
					display flex
					height 100upx
					margin-top 20upx
					.fangdajing
						width 50upx
						height 50upx
						margin-top 7upx
					.gouwuche
						width 60upx
						height 60upx
						margin-left 30upx
		.LoginPhoneContent
			width 750upx
			height 746upx
			position absolute
			left 0
			top 88upx
			.top
				width 750upx
				height 90upx
				text-align center
				margin 56upx 0 0
				image
					width 268upx
					height 90upx
			.center
				width 750upx
				padding 60upx 40upx 0
				input 
					display block
					width 670upx
					height 92upx
					line-height 92upx
					font-size 28upx
					border-bottom 1upx solid #a4a4a4
					box-sizing border-box
				.getCode
					width 670upx
					height 92upx
					.Code
						width 168upx
						height 54upx
						line-height 54upx
						text-align center
						color #333
						box-sizing border-box
						border 1upx solid #333
						font-size 28upx
						position absolute
						right 40upx
						top 320upx
				.in-forget
					width 670upx
					height 115upx
					line-height 115upx
					font-size 28upx
					color #666
					.new
						float left
					.forget
						float right
				.loginButton
					width 670upx
					height 92upx
					line-height 92upx
					text-align center
					color rgba(255,255,255,1)
					font-size 28upx
					background #dd1a21
					border-radius 3upx
				.other
					width 670upx
					height 38upx
					line-height 38upx
					text-align center
					color #333
					font-size 28upx
					margin-top 200upx
</style>
