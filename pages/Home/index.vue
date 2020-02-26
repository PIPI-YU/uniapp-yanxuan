<template>
	<view id="homeContainer">
		<view class="space"></view>
		<view class="homeHead">
			<view class="headTop">
				<image src="//yanxuan-static.nosdn.127.net/hxm/yanxuan-wap/p/20161201/style/img/icon-normal/indexLogo-a90bdaae6b.png" mode=""></image>
				<view class="search" @click="goSearch">
					<image src="../../static/images/Home/search.png" mode=""></image>
					<view class="searchText">搜索商品, 共22421款好物</view>
				</view>
				<view class="loginButton" @click="goPersonal">登录</view>
			</view>
			<view class="headBottom">
				<view class="hide" v-show="isHide">
					<scroll-view class="scroll-view" scroll-x="true">
							<view class="scroll-item">推荐</view>
							<view class="scroll-item">居家生活</view>
							<view class="scroll-item">服饰鞋包</view>
							<view class="scroll-item">美食酒水</view>
							<view class="scroll-item">个护清洁</view>
							<view class="scroll-item">母婴亲子</view>
							<view class="scroll-item">运动旅行</view>
							<view class="scroll-item">数码家电</view>
							<view class="scroll-item">全球特色</view>
					</scroll-view>
				</view>
				<view class="show" v-show="!isHide">
					<view class="showTop">全部频道</view>
					<view class="showBottom">
						<view class="show-item">推荐</view>
						<view class="show-item">居家生活</view>
						<view class="show-item">服饰鞋包</view>
						<view class="show-item">美食酒水</view>
						<view class="show-item">个护清洁</view>
						<view class="show-item">母婴亲子</view>
						<view class="show-item">运动旅行</view>
						<view class="show-item">数码家电</view>
						<view class="show-item">全球特色</view>
					</view>
					<view class="mask"></view>
				</view>
				<view class="arrow" @click="point(isHide)">
					<image src="//yanxuan-static.nosdn.127.net/hxm/yanxuan-wap/p/20161201/style/img/icon-normal/arrow-down-3-9b31adfa37.png" mode=""></image>
				</view>
			</view>
		</view>
		<view class="swiper-container">
			<swiper class="swiper" indicator-dots="true" autoplay="true" interval="2000" circular="true">
					<swiper-item>
							<image src="../../static/images/Home/swiper01.webp" mode=""></image>
					</swiper-item>
					<swiper-item>
							<image src="../../static/images/Home/swiper02.webp" mode=""></image>
					</swiper-item>
					<swiper-item>
							<image src="../../static/images/Home/swiper03.webp" mode=""></image>
					</swiper-item>
					<swiper-item>
							<image src="../../static/images/Home/swiper04.webp" mode=""></image>
					</swiper-item>
					<swiper-item>
							<image src="../../static/images/Home/swiper05.webp" mode=""></image>
					</swiper-item>
					<swiper-item>
							<image src="../../static/images/Home/swiper06.webp" mode=""></image>
					</swiper-item>
					<swiper-item>
							<image src="../../static/images/Home/swiper07.webp" mode=""></image>
					</swiper-item>
					<swiper-item>
							<image src="../../static/images/Home/swiper08.webp" mode=""></image>
					</swiper-item>
			</swiper>
		</view>
		<view class="homeService">
			<uni-list class="serviceList">
				<uni-list-item class="serviceItem" v-for="(serviceItem,index) in indexData.policyDescList" :key="index">
					<image :src="serviceItem.icon" mode=""></image>
					<view class="text">{{serviceItem.desc}}</view>
				</uni-list-item>
			</uni-list>
		</view>
		<view class="homeContent">
			<view class="kingKong">
				<view class="kingKongList">
					<view class="kingKongItem" v-for="(kkItem,index) in indexData.kingKongModule.kingKongList" :key="index">
						<image :src="kkItem.picUrl" mode=""></image>
						<view class="kingKongText">{{kkItem.text}}</view>
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
				isHide:true,
				indexData:{}
			}
		},
		onLoad(){
			uni.request({
				url:"http://localhost:3001/getIndexData",
				// dataType:"json",
				success:(data)=>{
					this.indexData = data.data;
					console.log(data);
					},
				fail:()=>{console.log("请求失败")}
			})
		},
		methods:{
			point(isHide){
				this.isHide = !isHide
			},
			goSearch(){
				uni.navigateTo({
					url:"../Search/index"
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
	#homeContainer
		width 750upx
		height 1334upx
		.space
			width 750upx
			height 148upx
		.homeHead
			width 750upx
			height 148upx
			background #fff
			position fixed
			left 0
			top 0
			z-index 1
			.headTop
				display flex
				align-items center
				width 750px
				height 88upx
				line-height 88px
				padding 0 30upx
				image
					display block
					width 138upx
					height 40upx
					margin-right 20upx
				.search
					display flex
					justify-content center
					width 442upx
					height 56upx
					line-height 56upx
					align-items center
					font-size 28upx
					border-radius 12.5upx
					background #ededed
					image
						width 28upx
						height 28upx
						margin-right 10upx
					.searchText
						font-size 28upx
						color #666
				.loginButton
					width 74upx
					height 40upx
					line-height 40upx
					text-align center
					border 1px solid #dd1a21
					color #DD1A21
					font-size 24upx
					margin-left 16upx
					border-radius 8upx
			.headBottom
				width 750upx
				height 60upx
				.hide
					width 750upx
					height 60upx
					.scroll-view
						display flex
						flex-wrap nowrap
						white-space nowrap
						box-sizing border-box
						width 650upx
						height 60upx
						.scroll-item
							display inline-block
							box-sizing border-box
							height 60upx
							line-height 60upx
							text-align center
							font-size 28upx
							padding 0 20upx
							margin-right 20upx
						.scroll-item:first-child
							margin-left 30upx
							color #dd1a21
							border-bottom 6upx solid #DD1A21
				.show
					width 750upx
					height 372upx
					background #fff
					position absolute
					left 0
					top 88upx
					.showTop
						width 720upx
						height 60upx
						line-height 60upx
						color #333
						font-size 28upx
						font-weight bold
						margin-left 30upx
					.showBottom
						display flex
						flex-wrap wrap
						width 720upx
						height 312upx
						padding 24upx 0
						margin-left 30upx
						.show-item
							width 150upx
							height 56upx
							line-height 56upx
							text-align center
							font-size 24upx
							color #333
							background #fafafa
							margin 0 30upx 40upx 0
							box-sizing border-box
							border 1px solid #ccc
						.show-item:first-child
							color #DD1A21
							border 1px solid #DD1A21
					.mask
						width 750upx
						height 874upx
						background rgba(0,0,0,0.5)
						z-index 1
				.arrow
					width 100upx
					height 60upx
					box-sizing border-box
					position absolute
					right 0
					top 88upx
					z-index 5
					image
						display block
						width 30upx
						height 30upx
						margin 18upx 35upx
		.swiper-container
			width 750upx
			height 370upx
			.swiper
				width 750upx
				height 370upx
				image
					width 750upx
					height 370upx
		.homeService
			width 750upx
			height 72upx
			.serviceList
				display flex
				justify-content space-between
				width 750upx
				height 72upx
				box-sizing border-box
				padding 0 30upx
				.serviceItem
					display flex
					height 36upx
					line-height 36upx
					margin-top 18upx 
					image
						width 32upx
						height 32upx
					.text
						color #333
						font-size 24upx
						margin 0 0 0 8upx
		.homeContent
			width 750upx
			height 1000upx
			.kingKong
				width 750upx
				height 372upx
				box-sizing border-box
				.kingKongList
					display flex
					flex-wrap wrap
					width 750upx
					.kingKongItem
						width 110upx
						height 156upx
						box-sizing border-box
						margin 15upx 20upx 10upx
						image
							width 110upx
							height 110upx
						.kingKongText
							width 110upx
							text-align center
							box-sizing border-box
							font-size #333
							font-size 24upx
</style>
