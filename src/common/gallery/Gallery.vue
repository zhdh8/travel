<template>
  <div class="container">
    <div class="wrapper">
      <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide>
        <img class="img-100" src="//img1.qunarzz.com/sight/201406/05/4c43fb96f4ab2526c8d65eac.jpg_600x330_1e857020.jpg" alt="">
      </swiper-slide>
      <swiper-slide>
        <img class="img-100" src="//img1.qunarzz.com/sight/201406/05/4c43fb96f4ab2526c8d65eac.jpg_600x330_1e857020.jpg" alt="">
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CommonGallery',
  data () {
    return {
      swiperOption: {
        autoplay: false,
        pagination: '.swiper-pagination',
        paginationType: 'fraction'
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
  .swiper-container
    overflow inherit
  .container
    width 100%
    height 100%
    display flex
    flex-direction column
    justify-content center
    background #000
    position fixed
    top 0
    left 0
    right 0
    bottom 0
    .wrapper
      width 100%
      height 0
      padding-bottom 60%
      .img-100
        width 100%
      .swiper-pagination
        bottom -1rem
        color #fff
</style>
