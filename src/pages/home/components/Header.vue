<template>
  <div class="header-wrapper">
    <div class="left-back">
      <i class="iconfont back-icon">&#xe60f;</i>
    </div>
    <div class="middle-input">
      <i class="iconfont search-icon">&#xe603;</i>
      <input type="text" placeholder="输入城市/景点/游玩主题">
    </div>
    <router-link to="/city">
      <div class="right-city">
        {{this.$store.state.city}} <i class="iconfont arrow-down-icon">&#xe60b;</i>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variables.styl'
  .header-wrapper
    line-height .86rem
    background-color $themeColor
    color #fff
    font-size .4rem
    display flex
    .left-back
      width .64rem
      .back-icon
        font-size .5rem
    .middle-input
      flex 1
      height .86rem
      position relative
      input
        border-radius .08rem
        width 88%
        height .6rem
        padding-left .5rem
        font-size .3rem
        &::placeholder
          color #ccc
      .search-icon
        height .6rem
        position absolute
        left .1rem
        top .03rem
        color #ccc
        font-size .4rem
    .right-city
      width 1rem
      font-size .26rem
      color #fff
      .arrow-down-icon
        font-size .28rem
</style>
