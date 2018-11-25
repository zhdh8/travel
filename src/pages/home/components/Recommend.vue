<template>
  <div>
    <div class="hot-recommend-title">
      热销推荐
    </div>
    <ul>
      <li class="item border-bottom">
        <img src="http://img1.qunarzz.com/sight/p0/1508/97/ea51af995c4d4de85c53855302b2f5af.water.jpg_250x250_a567aa64.jpg" alt="" class="item-img">
        <div class="item-info">
          <p class="info-title">观音山梦幻海岸车技演艺秀</p>
          <p class="info-desc">观音山梦幻海岸车技演艺秀</p>
          <button class="item-btn">查看详情</button>
        </div>
      </li>
      <li class="item border-bottom">
        <img src="http://img1.qunarzz.com/sight/p0/1508/97/ea51af995c4d4de85c53855302b2f5af.water.jpg_250x250_a567aa64.jpg" alt="" class="item-img">
        <div class="item-info">
          <p class="info-title">观音山梦幻海岸车技演艺秀</p>
          <p class="info-desc">观音山梦幻海岸车技演艺秀</p>
          <button class="item-btn">查看详情</button>
        </div>
      </li>
      <li class="item border-bottom">
        <img src="http://img1.qunarzz.com/sight/p0/1508/97/ea51af995c4d4de85c53855302b2f5af.water.jpg_250x250_a567aa64.jpg" alt="" class="item-img">
        <div class="item-info">
          <p class="info-title">观音山梦幻海岸车技演艺秀</p>
          <p class="info-desc">观音山梦幻海岸车技演艺秀</p>
          <button class="item-btn">查看详情</button>
        </div>
      </li>
      <li class="item border-bottom">
        <img src="http://img1.qunarzz.com/sight/p0/1508/97/ea51af995c4d4de85c53855302b2f5af.water.jpg_250x250_a567aa64.jpg" alt="" class="item-img">
        <div class="item-info">
          <p class="info-title">观音山梦幻海岸车技演艺秀</p>
          <p class="info-desc">观音山梦幻海岸车技演艺秀</p>
          <button class="item-btn">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeRecommend'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .hot-recommend-title
    line-height .8rem
    background-color #eee
    text-indent .4rem
    font-size .3rem
    margin-top .2rem
  .item
    display flex
    .item-img
      width 1.7rem
      height 1.7rem
      padding .1rem
    .item-info
      flex 1
      padding .1rem
      min-width 0
      .info-title
        line-height .54rem
        font-size .32rem
        ellipsis()
      .info-desc
        line-height .4rem
        color #ccc
        ellipsis()
      .item-btn
        padding 0 .2rem
        margin-top .16rem
        background-color orange
        color #fff
        border-radius .06rem
</style>
