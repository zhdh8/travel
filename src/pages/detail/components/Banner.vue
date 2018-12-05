<template>
  <div class="banner">
    <img class="banner-img" src="//img1.qunarzz.com/sight/201406/05/4c43fb96f4ab2526c8d65eac.jpg_600x330_1e857020.jpg" alt="">
    <div class="banner-info">
      <div class="title">大连圣亚海洋世界</div>
      <div class="number">
        <i class="iconfont">&#xe60f;</i> 39
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailBanner'
}
</script>

<style lang="stylus" scoped>
  .banner
    height 0
    padding-bottom 55%
    position relative
    .banner-img
      width 100%
    .banner-info
      position absolute
      left 0
      right 0
      bottom 0
      line-height .6rem
      display flex
      color #fff
      background-image linear-gradient(top, rgba(0,0,0,0), rgba(0,0,0,0.8))
      .title
        flex 1
        font-size 0.32rem
        padding 0.2rem
      .number
        background rgba(0,0,0,.4)
        padding 0 .4rem
        height .32rem
        line-height 0.32rem
        color #fff
        border-radius .2rem
        font-size 0.24rem
        margin-top 0.33rem
</style>
