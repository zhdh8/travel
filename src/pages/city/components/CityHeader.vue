<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <i class="iconfont back-icon">&#xe60f;</i>
    </router-link>
  </div>
</template>
<script>
export default {
  name: 'CityHeader'
}
</script>
<style lang="stylus" scoped>
  @import '~styles/variables.styl'
  .header
    line-height .86rem
    color #fff
    text-align center
    font-size 0.32rem
    background-color $themeColor
    position relative
    .back-icon
      position absolute
      left .15rem
      top 0
      color #fff
      font-size 0.5rem
</style>
