<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if="ifShow">
      <!-- slides -->
      <swiper-slide v-for="item of list" :key="item.id">
        <img class="img-100" :src="item.imgUrl" alt="">
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        loop: true,
        autoplay: 3000,
        pagination: {
          el: '.swiper-pagination'
        }
      }
    }
  },
  computed: {
    ifShow () {
      return this.list.length
    }
  }
}
</script>

<style lang="stylus" scoped>
  /*>>> 样式穿透*/
  .wrapper >>> .swiper-pagination-bullet-active
    background #fff !important
  .wrapper
    overflow hidden
    width 100%
    height 0
    padding-bottom 32.25%
    .img-100
      width 100%
</style>
