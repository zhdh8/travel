<template>
  <div>
    <div class="hot-recommend-title">
      热销推荐
    </div>
    <ul>
      <router-link class="item border-bottom" v-for="item of list" :key="item.id" tag="li" :to="'/detail/'+item.id">
        <img :src="item.imgUrl" alt="" class="item-img">
        <div class="item-info">
          <p class="info-title" v-text="item.title"></p>
          <p class="info-desc" v-text="item.desc"></p>
          <button class="item-btn">查看详情</button>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
  }
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
