<template>
  <div class="wrapper">
    <div class="one-level border-bottom" v-for="(item,index) of list" :key="index">
      <h3 class="one-title">
        <i class="iconfont scenery-icon">&#xe604;</i>
        {{item.title}}
      </h3>
      <div class="two-level" v-if="item.children">
        <detail-list :list="item.children"></detail-list>
        <div class="three-level border-bottom">
          三级内容介绍三级内容介绍三级内容介绍三级内容介绍三级内容介绍三级内容介绍三级内容介绍三级内容介绍三级内容介绍
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variables.styl'
  .wrapper
    padding 0 .2rem
    .one-level
      line-height 0.88rem
      .one-title
        color #333
        font-size 0.32rem
        .scenery-icon
          color $themeColor
          font-size .3rem
    .two-level
      padding .1rem 0
      font-size 0.3em
      line-height 0.35rem
      color #333
      text-indent 2em
    .three-level
      font-size 0.24em
      line-height 0.3rem
      color #888
      padding-bottom 0.2rem
</style>
