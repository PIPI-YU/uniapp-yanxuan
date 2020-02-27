<template>
  <view id="sortContainer">
    <view class="sortHead">
      <view class="headContent">
        <view class="input" @click="goSearch">
          <image src="../../static/images/Home/search.png" mode=""></image>
          <span>搜索商品，共21988款好物</span>
        </view>
      </view>
    </view>
    <view class="sortContent">
      <view class="left">
				<scroll-view class="leftList" scroll-y="true">
					<view class="leftItem" v-for="(leftItem,index) in sortNavData.categoryL1List" :key="index" @click="getId(leftItem.id)">{{leftItem.name}}</view>
				</scroll-view>
      </view>
      <scroll-view class="right" scroll-y="true">
        <view class="rightContent" v-for="(rightContent,index) in sortListData" :key="index">
        	<view v-if="rightContent.id===id">
						<view class="rightTop">
							<image src="../../static/images/Sort/top.png" mode=""></image>
						</view>
						<view class="rightList">
							<view class="rightItem" v-for="(rightItem,index) in rightContent.categoryList||rightContent.subCateList">
								<image :src="rightItem.wapBannerUrl" mode=""></image>
								<view class="text">{{rightItem.name}}</view>
							</view>
						</view>
        	</view>
        </view>
      </scroll-view>
    </view>
  </view>
</template>

<script type="text/ecmascript-6">
  export default {
    data(){
			return{
				sortNavData:{},
				sortListData:[],
				id:11
			}
		},
		onLoad(){
			uni.request({
				url:"http://localhost:3001/getSortNavData",
				success:(data)=>{
					this.sortNavData = data.data;
					console.log(data);
					},
				fail:()=>{console.log("请求左侧失败")}
			}),
			uni.request({
				url:"http://localhost:3001/getSortListData",
				success:(data)=>{
					this.sortListData = data.data;
					console.log(data);
					},
				fail:()=>{console.log("请求右侧失败")}
			})
		},
    methods:{
			goSearch(){
				uni.navigateTo({
					url:"../Search/index"
				})
			},
			getId(id){
				this.id = id
			}
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
#sortContainer
  width 750upx
  height 100%
  .sortHead
    display flex
    vertical-align middle
    width 750upx
    height 88upx
    background #fff
    border-bottom 1upx solid rgba(0,0,0,.15)
    position fixed
    left 0
    top 0
    z-index 1
    .headContent
      display flex
      width 690upx
      height 56upx
      line-height 56upx
      margin auto
      font-size 28upx
      border-radius 8upx
      color #666
      background #ededed
      .input
        height 56upx
        line-height 56upx
        margin 0 auto
        image
          width 28upx
          height 28upx
          margin-right 10upx
  .sortContent
    display flex
    width 750upx
    height 1000upx
    position absolute
    left 0
    top 88upx
    .left
      width 162upx
      background #fff
      border-right 1upx solid rgba(0,0,0,.15)
			.leftList
				width 162upx
				height 1000upx
				padding 40upx 0
				box-sizing border-box
				.leftItem
					list-style none
					width 162upx
					height 50upx
					line-height 50upx
					font-size 28upx
					text-align center
					margin-bottom 30upx
					box-sizing border-box
					color #333
				.leftItem:first-child
					color #ab2b2b
					border-left 6upx solid #ab2b2b
    .right
      width 588upx
      height 1148upx
			.rightContent
				width 528upx
				margin 20upx 30upx 0
				.rightTop
					width 528upx
					height 192upx
					margin-bottom 32upx
					image
						width 528upx
						height 192upx
				.rightList
					display flex
					flex-wrap wrap
					justify-content space-around
					width 528upx
					.rightItem
						width 144upx
						height 216upx
						image
							width 144upx
							height 144upx
						.text
							width 144upx
							height 72upx
							line-height 36upx
							text-align center
							color #333333
							font-size 24upx
</style>
