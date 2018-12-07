<template>
  <div class="alphabet" ref="alphabet-wrapper">
    <ul>
      <li v-for="item of letters" :key="item" :ref="item" class="item" v-text="item" @click="handleClick" @touchstart.prevent="handleTouchStart" @touchmove="handleTouchMove" @touchend="handleTouchEnd">A</li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  },
  data () {
    return {
      touchStatus: false,
      startY: 0,
      timer: null
    }
  },
  methods: {
    handleClick (e) {
      // console.log(e.target.innerText)
      this.$emit('change', e.target.innerText)
    },
    handleTouchStart () {
      this.touchStatus = true
    },
    handleTouchMove (e) {
      // console.log(e)
      if (this.touchStatus) {
        // 字母距离顶部的top值
        // const startY
        // 滑动手指到屏幕顶端的距离
        if (this.timer) {
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          const scrollY = e.touches[0].clientY
          const index = Math.floor((scrollY - this.startY) / 20)
          if (index >= 0 && index < this.letters.length) {
            this.$emit('change', this.letters[index])
          }
        }, 16)
      }
    },
    handleTouchEnd () {
      this.touchStatus = false
    }
  },
  computed: {
    letters () {
      const letters = []
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  updated () {
    this.startY = this.$refs['alphabet-wrapper'].offsetTop
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
      line-height 0.4rem
      font-size 0.3rem
      text-align center
      color $themeColor
</style>
