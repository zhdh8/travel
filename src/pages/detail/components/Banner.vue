<template>
  <div>
    <div class="banner" @click="handleGalleryShow">
      <img class="banner-img" :src="bannerImg" alt="">
      <div class="banner-info">
        <div class="title">{{sightName}}</div>
        <div class="number">
          <i class="iconfont book-icon">&#xe63d;</i> {{imgNum}}
        </div>
      </div>
    </div>
    <fade-animation>
      <common-gallery v-show="showGallery" @close="handleGalleryClose" :bannerImgs="bannerImgs"></common-gallery>
    </fade-animation>
  </div>
</template>

<script>
import CommonGallery from 'common/gallery/Gallery'
import FadeAnimation from 'common/fade/Fade'
export default {
  name: 'DetailBanner',
  props: {
    sightName: String,
    bannerImg: String,
    bannerImgs: Array
  },
  components: {
    CommonGallery,
    FadeAnimation
  },
  data () {
    return {
      showGallery: false
    }
  },
  methods: {
    handleGalleryShow () {
      this.showGallery = true
    },
    handleGalleryClose () {
      this.showGallery = false
    }
  },
  computed: {
    imgNum () {
      return this.bannerImgs.length
    }
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    height 0
    padding-bottom 55%
    position relative
    .banner-img
      width 100%
    .banner-info
      position absolute
      left 0
      right 0
      bottom 0
      line-height .6rem
      display flex
      color #fff
      background-image linear-gradient(top, rgba(0,0,0,0), rgba(0,0,0,0.8))
      .title
        flex 1
        font-size 0.32rem
        padding 0 0.2rem
      .number
        background rgba(0,0,0,.8)
        padding 0 .4rem
        height .32rem
        line-height 0.32rem
        color #fff
        border-radius .2rem
        font-size 0.24rem
        margin-top 0.14rem
        .book-icon
          font-size 0.3rem
</style>
