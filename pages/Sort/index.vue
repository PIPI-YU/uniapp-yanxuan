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
        <view class="BScroll">
          <scroll-view class="leftList" scroll-x="true">
            <view class="leftItem" v-for="(leftItem,index) in sortNavData.categoryL1List" :key="index">{{leftItem.name}}</view>
          </scroll-view>
        </view>
      </view>
      <view class="right">
        <router-view></router-view>
      </view>
    </view>
  </view>
</template>

<script type="text/ecmascript-6">
  export default {
    data(){
			return{
				sortNavData:{},
				sortListData:[]
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
			}
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
#sortContainer
  width 750upx
  height 100%
  position relative
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
    height 1148upx
    position absolute
    left 0
    top 88upx
    .left
      width 162upx
      height 1148upx
      background #fff
      border-right 1upx solid rgba(0,0,0,.15)
      .BScroll
        width 162upx
        height 1120upx
        .leftList
          width 162upx
          padding 40upx 0
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
 
</style>
