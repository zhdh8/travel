<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item of imgList" :key="item.id">
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
  data () {
    return {
      swiperOption: {
        loop: true,
        autoplay: 3000,
        pagination: {
          el: '.swiper-pagination'
        }
      },
      imgList: [
        {id: '001', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1811/7c/8e5c4ab8ee8b7402.jpg_750x200_dd7a38dd.jpg'},
        {id: '002', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1809/d4/e298dff35d3af802.jpg_750x200_9b0d56c1.jpg'},
        {id: '003', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1809/12/856f100069809e02.jpg_750x200_e3485a2b.jpg'}
      ]
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
    padding-bottom 26.25%
    .img-100
      width 100%
</style>
