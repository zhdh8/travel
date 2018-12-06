<template>
  <div class="container" @click="handleShow">
    <div class="wrapper">
      <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="(item,index) of bannerImgs" :key="index">
        <img class="img-100" :src="item" alt="">
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
  props: {
    bannerImgs: Array
  },
  data () {
    return {
      swiperOption: {
        autoplay: false,
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observeParents: true,
        observer: true
      }
    }
  },
  methods: {
    handleShow () {
      this.$emit('close')
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
    z-index 9
    .wrapper
      width 100%
      height 0
      padding-bottom 100%
      .img-100
        width 100%
      .swiper-pagination
        bottom -1rem
        color #fff
</style>
