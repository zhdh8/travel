<template>
  <div class="alphabet">
    <ul>
      <li v-for="(item, key) of cities" :key="key" class="item" v-text="key" @click="handleClick" ref="letter">A</li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  },
  methods: {
    handleClick (e) {
      // console.log(e.target.innerText)
      this.$emit('change', e.target.innerText)
    }
  }
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
