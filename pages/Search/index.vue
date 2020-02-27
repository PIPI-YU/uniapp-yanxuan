<template>
  <view id="searchContainer">
      <view class="searchContent">
        <view class="searchTop">
          <view class="inputContainer">
            <image class="img" src="../../static/images/Home/search.png" mode=""></image>
            <input class="text" type="text" :placeholder="searchListData.defaultKeyword.keyword"/>
          </view>
          <span class="cancel" @click="goHome">取消</span>
        </view>
        <view class="searchBottom">
          <view class="header">
            <h3>热门搜索</h3>
          </view>
          <view class="list">
            <view v-for="(searchItem, index) in searchListData.hotKeywordVOList" :key="index" class="listItem">
              <span>{{searchItem.keyword}}</span>
            </view>
          </view>
        </view>
      </view>
      <view class="mask"></view>
  </view>
</template>

<script type="text/ecmascript-6">
  export default {
		data(){
			return{
				searchListData:{}
			}
		},
		onLoad(){
			uni.request({
				url:"https://m.you.163.com/xhr/search/init.json",
				success:(data)=>{
					this.searchListData = data.data.data;
					console.log(data);
					},
				fail:()=>{console.log("请求searchList失败")}
			})
		},
		methods:{
			goHome(){
				uni.switchTab({
					url:"../Home/index"
				})
			}
		}
	}
</script>

<style lang="stylus" rel="stylesheet/stylus">
	#searchContainer
		width 750upx
		height 1334upx
		white-space nowrap
		position absolute
		left 0
		top 0
		background #fff
		.searchContent
			width 750upx
			height 523upx
			.searchTop
				display flex
				width 750upx
				height 88upx
				line-height 88upx
				border 1upx solid #fff
				box-sizing border-box
				padding 0 30upx
				.inputContainer
					display flex
					width 604upx
					height 56upx
					line-height 56upx
					background #f4f4f4
					box-sizing border-box
					padding 0 20upx
					margin auto 0
					.img
						width 28upx
						height 28upx
						margin 15upx 16upx 0 0
					.text
						width 520upx
						height 39upx
						font-size 28upx
						background #f4f4f4
						box-sizing border-box
						color rgba(0,0,0,0.8)
						padding 0 0 0 2upx
						margin auto 0
				.cancel
					width 56upx
					height 42upx
					color #333
					font-size 28upx
					margin 0 0 0 30upx
			.searchBottom
				width 750upx
				height 436upx
				.header
					width 690upx
					height 90upx
					line-height 90upx
					margin 0 auto
					h3
						font-size 28upx
						color #999
				.list
					display flex
					flex-wrap wrap
					width 720upx
					margin 0 30upx 32upx 30upx
					.listItem
						display block
						font-size 24upx
						color #333
						line-height 46upx
						margin 0 32upx 32upx 0
						padding 0 15upx
						border 1upx solid #999
						border-radius 4upx
						box-sizing border-box
					.listItem:first-child
						color #dd1a21
						border 1upx solid #dd1a21
		.mask
			width 750upx
			height 811upx
			background #ededed
</style>
