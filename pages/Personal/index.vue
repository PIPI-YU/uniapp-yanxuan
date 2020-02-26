<template>
	<view id="personalContainer">
		<view class="personalHead">
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
		<view class="personalContent">
			<view class="top">
				<view class="image">
					<image src="../../static/images/Personal/yanxuan.png" mode=""></image>
				</view>
				<view class="loginButton">
					<view class="phone" @click="goPhone">
						<image src="../../static/images/Personal/phone.png" mode=""></image>
						<view class="text">手机号快捷登录</view>
					</view>
					<view class="email" @click="goEmail">
						<image src="../../static/images/Personal/email.png" mode=""></image>
						<view class="text">邮箱账号登录</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
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
			goPhone(){
				uni.navigateTo({
					url:"../Login/Phone"
				})
			},
			goEmail(){
				uni.navigateTo({
					url:"../Login/Email"
				})
			}
		}
	}
</script>

<style lang="stylus" rel="stylesheet/stylus">
	#personalContainer
		width 750upx
		height 1334upx
		box-sizing border-box
		.personalHead
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
		.personalContent
			width 750upx
			height 1246upx
			position absolute
			left 0
			top 88upx
			background #F2F5F4
			.top
				width 750upx
				overflow hidden
				.image
					width 750upx
					height 482upx
					line-height 482upx
					overflow hidden
					image
						display block
						width 268upx
						height 90upx
						margin 196upx auto
				.loginButton
					width 750upx
					padding 0 40upx
					.phone
						display flex
						width 670upx
						height 94upx
						line-height 94upx
						text-align center
						color #ffffff
						background #dd1a21
						margin 0 0 32upx
						image
							width 40upx
							height 40upx
							margin 27upx 16upx 0 220upx
						.text
							font-size 30upx
					.email
						display flex
						width 670upx
						height 94upx
						line-height 94upx
						text-align center
						color  #dd1a21
						border 1upx solid #dd1a21
						box-sizing border-box
						image
							width 40upx
							height 40upx
							margin 27upx 16upx 0 220upx
						.text
							font-size 30upx
</style>
