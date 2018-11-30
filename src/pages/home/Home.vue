<template>
  <div>
    <home-header></home-header>
    <home-swiper :list="swiperList"></home-swiper>
    <home-icons :list="iconList"></home-icons>
    <home-recommend :list="recommendList"></home-recommend>
    <home-weekend :list="weekendList"></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'
import axios from 'axios'
export default {
  name: 'Home',
  data () {
    return {
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    }
  },
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  methods: {
    getHomeInfo () {
      axios.get('api/index.json').then((res) => {
        res = res.data
        if (res.ret && res.data) {
          // console.log(res.data)
          this.iconList = res.data.iconList
          this.swiperList = res.data.swiperList
          this.recommendList = res.data.recommendList
          this.weekendList = res.data.weekendList
        }
      }).catch((error) => {
        console.log(error)
      })
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>

<style>

</style>
