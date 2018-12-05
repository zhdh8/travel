<template>
  <div>
    <div class="week-recommend-title">
      周末去哪儿
    </div>
    <ul>
      <li class="item border-bottom" v-for="item of list" :key="item.id">
        <div class="img-wrapper">
          <img :src="item.imgUrl" alt="" class="item-img">
        </div>
        <div class="item-info">
          <p class="info-title" v-text="item.title">观音山梦幻海岸车技演艺秀</p>
          <p class="info-desc" v-text="item.desc">观音山梦幻海岸车技演艺秀</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .week-recommend-title
    line-height .8rem
    background-color #eee
    text-indent .4rem
    font-size .3rem
  .img-wrapper
    height 0
    padding-bottom 33.9%
    overflow hidden
    .item-img
      width 100%
  .item-info
    padding .3rem
    min-width 0
    .info-title
      line-height .54rem
      font-size .32rem
      ellipsis()
    .info-desc
      line-height .4rem
      color #616161
      ellipsis()
</style>
