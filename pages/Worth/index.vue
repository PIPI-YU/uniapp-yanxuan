<template>
  <view id="worthContainer">
		<view class="worthHead">
			<view class="header">
				<view class="left">
					<image src="../../static/images/Worth/home02.png" mode="" @click="goHome"></image>
				</view>
				<view class="center">值得买</view>
				<view class="right">
					<image class="fangdajing" src="../../static/images/Worth/search.png" mode="" @click="goSearch"></image>
					<image class="gouwuche" src="../../static/images/Worth/cart02.png" mode="" @click="goCart"></image>
				</view>
			</view>
		</view>
		<view class="worthNav">
			<view class="navTop">
				<image class="worth" src="../../static/images/Worth/worth.png" alt=""></image>
				<view class="navText">严选好物 用心生活</view>
			</view>
			<view class="navBottom">
				<view class="swiper-container">
					<scroll-view class="swiper-wrapper" scroll-x="true">
						<view class="swiper-slide">
							<view class="slideItem">
								<image :src="worthNavData.navList[0].picUrl" alt=""></image>
								<view class="itemText1">{{worthNavData.navList[0].mainTitle}}</view>
								<view class="itemText2">{{worthNavData.navList[0].viceTitle}}</view>
							</view>
							<view class="slideItem">
								<image :src="worthNavData.navList[1].picUrl" alt=""></image>
								<view class="itemText1">{{worthNavData.navList[1].mainTitle}}</view>
								<view class="itemText2">{{worthNavData.navList[1].viceTitle}}</view>
							</view>
						</view>
						<view class="swiper-slide">
							<view class="slideItem">
								<image :src="worthNavData.navList[2].picUrl" alt=""></image>
								<view class="itemText1">{{worthNavData.navList[2].mainTitle}}</view>
								<view class="itemText2">{{worthNavData.navList[2].viceTitle}}</view>
							</view>
							<view class="slideItem">
								<image :src="worthNavData.navList[3].picUrl" alt=""></image>
								<view class="itemText1">{{worthNavData.navList[3].mainTitle}}</view>
								<view class="itemText2">{{worthNavData.navList[3].viceTitle}}</view>
							</view>
						</view>
						<view class="swiper-slide">
							<view class="slideItem">
								<image :src="worthNavData.navList[4].picUrl" alt=""></image>
								<view class="itemText1">{{worthNavData.navList[4].mainTitle}}</view>
								<view class="itemText2">{{worthNavData.navList[4].viceTitle}}</view>
							</view>
							<view class="slideItem">
								<image :src="worthNavData.navList[5].picUrl" alt=""></image>
								<view class="itemText1">{{worthNavData.navList[5].mainTitle}}</view>
								<view class="itemText2">{{worthNavData.navList[5].viceTitle}}</view>
							</view>
						</view>
						<view class="swiper-slide">
							<view class="slideItem">
								<image :src="worthNavData.navList[6].picUrl" alt=""></image>
								<view class="itemText1">{{worthNavData.navList[6].mainTitle}}</view>
								<view class="itemText2">{{worthNavData.navList[6].viceTitle}}</view>
							</view>
							<view class="slideItem">
								<image :src="worthNavData.navList[7].picUrl" alt=""></image>
								<view class="itemText1">{{worthNavData.navList[7].mainTitle}}</view>
								<view class="itemText2">{{worthNavData.navList[7].viceTitle}}</view>
							</view>
						</view>
						<view class="swiper-slide">
							<view class="slideItem">
								<image :src="worthNavData.navList[8].picUrl" alt=""></image>
								<view class="itemText1">{{worthNavData.navList[8].mainTitle}}</view>
								<view class="itemText2">{{worthNavData.navList[8].viceTitle}}</view>
							</view>
							<view class="slideItem">
								<image :src="worthNavData.navList[9].picUrl" alt=""></image>
								<view class="itemText1">{{worthNavData.navList[9].mainTitle}}</view>
								<view class="itemText2">{{worthNavData.navList[9].viceTitle}}</view>
							</view>
						</view>
						<view class="swiper-slide">
							<view class="slideItem">
								<image :src="worthNavData.navList[10].picUrl" alt=""></image>
								<view class="itemText1">{{worthNavData.navList[10].mainTitle}}</view>
								<view class="itemText2">{{worthNavData.navList[10].viceTitle}}</view>
							</view>
							<view class="slideItem">
								<image :src="worthNavData.navList[11].picUrl" alt=""></image>
								<view class="itemText1">{{worthNavData.navList[11].mainTitle}}</view>
								<view class="itemText2">{{worthNavData.navList[11].viceTitle}}</view>
							</view>
						</view>
						<view class="swiper-slide">
							<view class="slideItem">
								<image :src="worthNavData.navList[12].picUrl" alt=""></image>
								<view class="itemText1">{{worthNavData.navList[12].mainTitle}}</view>
								<view class="itemText2">{{worthNavData.navList[12].viceTitle}}</view>
							</view>
							<view class="slideItem">
								<image :src="worthNavData.navList[13].picUrl" alt=""></image>
								<view class="itemText1">{{worthNavData.navList[13].mainTitle}}</view>
								<view class="itemText2">{{worthNavData.navList[13].viceTitle}}</view>
							</view>
						</view>
						<view class="swiper-slide">
							<view class="slideItem">
								<image :src="worthNavData.navList[14].picUrl" alt=""></image>
								<view class="itemText1">{{worthNavData.navList[14].mainTitle}}</view>
								<view class="itemText2">{{worthNavData.navList[14].viceTitle}}</view>
							</view>
							<view class="slideItem">
								<image :src="worthNavData.navList[15].picUrl" alt=""></image>
								<view class="itemText1">{{worthNavData.navList[15].mainTitle}}</view>
								<view class="itemText2">{{worthNavData.navList[15].viceTitle}}</view>
							</view>
						</view>
					</scroll-view>
				</view>
			</view>
		</view>
		<view class="space"></view>
		<view class="worthContent" v-for="(itemPage, index) in worthPoolData" :key="index">
			<view class="page">
				<view class="ad">
					<image class="ad-image" :src="itemPage.ad.picUrl" alt=""></image>
				</view>
				<view class="topics">
					<view class="topic" v-for="(item, index) in itemPage.topics" :key="index">
						<image class="image" :src="item.picUrl" alt=""></image>
						<view class="topic-title">{{item.title}}</view>
						<view class="topic-bottom">
							<view class="bottomLeft">
								<image class="avatar" :src="item.avatar" alt=""></image>
								<view class="topic-nickname">{{item.nickname}}</view>
							</view>
							<view class="bottomRight">90K</view>
						</view>
					</view>
				</view>
			</view>
		</view>
  </view>
</template>

<script type="text/ecmascript-6">
  export default {
    data(){
			return{
				worthNavData:{},
				worthPoolData:[]
			}
		},
		onLoad(){
			uni.request({
				url:"https://m.you.163.com/topic/v1/know/navWap.json",
				success:(data)=>{
					this.worthNavData = data.data.data;
					console.log(data);
					},
				fail:()=>{console.log("请求worth-nav失败")}
			}),
			uni.request({
				url:"https://m.you.163.com/topic/v1/find/recManual.json",
				success:(data)=>{
					this.worthPoolData = data.data.data;
					console.log(data);
					},
				fail:()=>{console.log("请求worth-pool失败")}
			})
		},
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
			}
		}
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
	#worthContainer
		width 750upx
		height 1334upx
		background #eee
		box-sizing border-box
		.worthHead
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
					width 150upx
					height 100upx
					line-height 100upx
					margin 0 150upx 0 215upx
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
		.worthNav
			width 750upx
			height 685upx
			position absolute
			left 0
			top 100upx
			background-image url("//m.you.163.com/topic/index/img/topic_title_bg.2373a140.png")
			background-repeat norepeat
			background-size 750upx 685upx
			background-position 0 0
			background-color #eee
		  .navTop
				display flex
				width 750upx
				height 140upx
				.worth
					width 130upx
					height 65upx
					position absolute
					left 13upx
					top 63upx
				.navText
					font-size 30upx
					position absolute
					color #fff
					left 150upx
					top 88upx
			.navBottom
				width 710upx
				height 540upx
				margin 0 20upx
				background #fff
				border-radius 24upx
				.swiper-container
					width 710upx
					height 540upx
					background #fff
					border-radius 24upx
					.swiper-wrapper
						display flex
						flex-wrap nowrap
						white-space nowrap
						width 710upx
						height 540upx
						.swiper-slide
							display inline-block
							overflow hidden
							width 177.5upx
							height 540upx
							.slideItem
								width 168upx
								height 201upx
								margin 45upx 4.75upx 0
								box-sizing border-box
								image
									width 120upx
									height 120upx
									margin 0 24upx
								.itemText1
									width 168upx
									height 40upx
									text-align center
									font-weight bold
									font-size 28upx
									color #333
								.itemText2
									width 168upx
									height 30upx
									text-align center
									font-size 24upx
									margin 2upx 0 0
									color #999
		.space
			width 750upx
			height 30upx
			background #eee
			position absolute
			left 0
			top 780upx
		.worthContent
			width 750upx
			background #eee
			box-sizing border-box
			position absolute
			left 0
			top 810upx
			overflow hidden
			.page
				width 750upx
				margin 0 10upx
				box-sizing border-box
				columns 2
				column-gap 20upx
				.ad
					width 345upx
					height 192upx
					border-radius 24upx
					font-size 0
					margin-bottom 20upx
					.ad-image
						display block
						width 345upx
						height 192upx
						border-radius 24upx
						margin-right 0
				.topics
					width 345upx
					border-radius 24upx
					.topic
						width 345upx
						background #fff
						border-radius 24upx
						margin-bottom 20upx
						overflow hidden
						break-inside avoid
						.image
							width 345upx
							height 192upx
							border-radius 24upx 24upx 0 0
						.topic-title
							width 345upx
							line-height 45upx
							color #333
							font-size 28upx
							padding 18upx 16upx 0
							box-sizing border-box
						.topic-bottom
							width 345upx
							height 80upx
							line-height 80upx
							padding 17upx 16upx 24upx
							box-sizing border-box
							.bottomLeft
								float left
								display flex
								height 48upx
								margin-top 20upx
								.avatar
									width 48upx
									height 48upx
									border-radius 24upx
								.topic-nickname
									height 48upx
									line-height 48upx
									color #7f7f7f
									font-size 24upx
									margin 0 0 0 8upx
							.bottomRight
								float right
								color #7f7f7f
								font-size 24upx
								margin 0 0 0 4upx
</style>
