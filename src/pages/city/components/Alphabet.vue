<template>
  <div class="alphabet">
    <ul>
      <li class="item">A</li>
      <li class="item">B</li>
      <li class="item">B</li>
      <li class="item">B</li>
      <li class="item">B</li>
      <li class="item">B</li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'CityAlphabet'
}
</script>
<style lang="stylus" scoped>
  @import '~styles/variables.styl'
  .alphabet
    display flex
    flex-direction column
    justify-content center
    position absolute
    top 2.6rem
    right 0
    width 0.4rem
    .item
      line-height 0.44rem
      font-size 0.3rem
      text-align center
      color $themeColor
</style>
