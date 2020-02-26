<template>
  <view id="cartContainer">
    <!-- 头部 -->
    <view class="cartHeader">
      <span class="leftTxt">购物车</span>
      <span class="rightTxt">领券</span>
    </view>
    <!-- 主要内容 -->
    <view class="cartContent">
      <view class="server">
        <view class="serverList">
          <view class="serverItem">30天无忧退货</view>
          <view class="serverItem">48小时快速退款</view>
          <view class="serverItem">满88元免邮费</view>
        </view>
      </view>
      <view class="login">
        <view class="cartBg"></view>
        <view class="loginBtn">
          <span>去添加点什么吧</span>
          <view class="login" @click="goPersonal">登录</view>
        </view>
      </view>
    </view>
	</view>
</template>

<script>
export default {
	methods:{
		goPersonal(){
			uni.switchTab({
				url:"../Personal/index"
			})
		}
	}
}
</script>

<style lang="stylus" rel="stylesheet/stylus">
#cartContainer
  width 100%
  // 头部
  .cartHeader
    display flex
    justify-content space-between
    width 100%
    height 88upx
    line-height 88upx
    padding 0 30upx
    box-sizing border-box
    .leftTxt
      font-size 36upx
      color #333
    .rightTxt
      margin-right 30upx
      font-size 30upx
      color red
  // 主要内容
  .cartContent
    width 100%
    .server
      width 100%
      height 70upx
      line-height 70upx
      background-color #eee
      padding 0 30upx
      box-sizing border-box
      .serverList
        display flex
        justify-content space-between
        width 100%
        height 100%
        .serverItem
          width 33%
          height 100%
          color #666
          text-align center
					font-size 24upx
    // 登录
    .login
      width 100%
      position absolute
      left 50%
      transform translateX(-50%)
      top 350upx
      .cartBg
        width 248upx
        height 248upx
        margin 0 auto
        background url('http://yanxuan-static.nosdn.127.net/hxm/yanxuan-wap/p/20161201/style/img/icon-normal/noCart-d6193bd6e4.png?imageView&type=webp') no-repeat
        background-size cover
      .loginBtn
        width 100%
        text-align center
        >span 
          font-size 28upx
          color #999
        .login
          width 480upx
          height 92upx
          line-height 92upx
          background-color #DD1A21
          margin 50upx auto 0
          font-size 30upx
          color #fff
 
</style>
