<template>
  <div class="wrapper" ref="wrapper">
    <div class="content">
      <div class="areas">
        <div class="list-title border-topbottom">您的位置</div>
        <div class="list-wrapper">
          <ul>
            <li class="button-wrapper"><div class="button">{{this.$store.state.city}}</div></li>
          </ul>
        </div>
      </div>
      <div class="areas">
        <div class="list-title border-topbottom">热门城市</div>
        <div class="list-wrapper">
          <ul>
            <li v-for="item of hot" :key="item.id" @click="handleChangeCity(item.name)" class="button-wrapper"><div class="button" v-text="item.name">龙岩</div></li>
          </ul>
        </div>
      </div>
      <div class="areas" v-for="(item, key) of cities" :key="key" :ref="key">
        <div class="list-title border-topbottom" v-text="key">A</div>
        <div class="city-wrapper">
          <ul>
            <li v-for="innerItem of item" :key="innerItem.id" class="city-item border-bottom" v-text="innerItem.name" @click="handleChangeCity(innerItem.name)">阿拉尔</li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import BScroll from 'better-scroll'
export default {
  name: 'CityList',
  props: {
    cities: Object,
    hot: Array,
    letter: String
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  },
  watch: {
    letter () {
      if (this.letter) {
        const ele = this.$refs[this.letter][0]
        this.scroll.scrollToElement(ele)
      }
    }
  },
  methods: {
    handleChangeCity (city) {
      this.$store.commit('changeCity', city)
      this.$router.push('/')
    }
  }
}
</script>
<style lang="stylus" scoped>
  .wrapper
    position absolute
    top 1.6rem
    left 0
    right 0
    bottom 0
    overflow hidden
    .areas
      .list-title
        line-height .7rem
        padding-left .25rem
        font-size .24rem
        color #212121
        background-color #f5f5f5
      .list-wrapper
        padding .1rem .9rem .1rem .2rem
        overflow hidden
        .button-wrapper
          float left
          width 33.33%
          .button
            margin 0.1rem
            padding 0.1rem 0
            text-align center
            border .02rem solid #ccc
            border-radius .04rem
      .city-wrapper
        .city-item
          line-height 0.76rem
          padding-left 0.2rem
</style>
