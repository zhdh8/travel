<template>
  <div>
    <div class="header-back" v-show="showHeaderAbs">
      <router-link tag="i" to="/" class="iconfont back-icon">&#xe60f;</router-link>
    </div>
    <div class="header-fixed" v-show="!showHeaderAbs" :style="opacityStyle">
        <router-link to="/">
          <i class="iconfont back-icon">&#xe60f;</i>
        </router-link>
        景点详情
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showHeaderAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      // console.log(top)
      if (top > 86) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.showHeaderAbs = false
      } else {
        this.showHeaderAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    // 销毁全局事件
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variables.styl'
  .header-back
    position absolute
    top 0.2rem
    left 0.2rem
    background rgba(0, 0, 0, 0.6)
    color #ffffff
    width .8rem
    height .8rem
    line-height 0.8rem
    border-radius .4rem
    text-align center
    .back-icon
      font-size 0.5rem
      color #fff
  .header-fixed
    position fixed
    top 0
    left 0
    right 0
    line-height .86rem
    color #fff
    text-align center
    font-size 0.32rem
    background-color $themeColor
    z-index 2
    .back-icon
      position absolute
      left .15rem
      top 0
      color #fff
      font-size 0.5rem
</style>
