<template>
 <div class="wrapper">
  <swiper :options="swiperOption">
    <swiper-slide v-for="(page, index) of pages" :key="index">
      <div class="items" v-for="item of page" :key="item.id">
        <div class="icon-wrapper">
          <img class="icon" :src="item.imgUrl" alt="">
        </div>
        <p class="info">{{item.info}}</p>
      </div>
    </swiper-slide>
  </swiper>
 </div>
</template>
<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      swiperOption: {
        autoplay: false
      },
      list: [
        {id: '001', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png', info: '景点门票'},
        {id: '002', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png', info: '景点门票'},
        {id: '003', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png', info: '景点门票'},
        {id: '004', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png', info: '景点门票'},
        {id: '005', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png', info: '景点门票'},
        {id: '006', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png', info: '景点门票'},
        {id: '007', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png', info: '景点门票'},
        {id: '008', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png', info: '景点门票'},
        {id: '009', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png', info: '景点门票'}
      ]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>
<style lang="stylus" scoped>
  @import '~styles/variables.styl'
  @import '~styles/mixins.styl'
  .wrapper >>> .swiper-container
    height 0
    padding-bottom 50%
  .wrapper
    margin-top .1rem
    .items
      position relative
      float left
      width 25%
      height 0
      padding-bottom 25%
      .icon-wrapper
        position absolute
        top 0
        left 0
        right 0
        bottom .44rem
        padding .1rem
        box-sizing border-box
        .icon
          height 100%
          display block
          margin 0 auto
      .info
        position absolute
        left 0
        right 0
        bottom 0
        height .44rem
        line-height .44rem
        text-align center
        color $themeTxtColor
        ellipsis()
</style>
