<template>
  <div>
    <div class="search">
      <input class="search-input" type="text" placeholder="输入城市名或拼音" v-model="keywords">
    </div>
    <div class="search-content" v-show="keywords">
      <ul>
        <li v-for="item of list" :key="item.id" class="border-bottom search-item" @click="handleChangeCity(item.name)">{{item.name}}</li>
        <li class="border-bottom search-item" v-show="hasData">没有找到您搜索的城市</li>
      </ul>
    </div>
  </div>
</template>
<script>
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keywords: '',
      list: []
    }
  },
  computed: {
    hasData () {
      return !this.list.length
    }
  },
  methods: {
    handleChangeCity (city) {
      this.$store.commit('changeCity', city)
      this.$router.push('/')
    }
  },
  watch: {
    keywords () {
      const result = []
      if (!this.keywords) {
        this.list = []
      }
      for (let i in this.cities) {
        this.cities[i].forEach((value) => {
          if (value.name.indexOf(this.keywords) > -1 || value.spell.indexOf(this.keywords) > -1) {
            result.push(value)
          }
        })
      }
      this.list = result
    }
  }
}
</script>
<style lang="stylus" scoped>
  @import '~styles/variables.styl'
  .search
    height 0.72rem
    background-color $themeColor
    padding 0 0.1rem
    .search-input
      width 100%
      height 0.62rem
      line-height 0.62rem
      text-align center
      border-radius .06rem
      color #666
  .search-content
    z-index 1
    background-color #eee
    overflow hidden
    position absolute
    top 1.58rem
    left 0
    right 0
    bottom 0
    .search-item
      line-height 0.6rem
      background-color #fff
      padding 0 .2rem
</style>
