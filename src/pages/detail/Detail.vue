<template>
  <div>
    <detail-banner></detail-banner>
    <common-gallery></common-gallery>
  </div>
</template>

<script>
import DetailBanner from './components/Banner'
import CommonGallery from 'common/gallery/Gallery'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    CommonGallery
  }
}
</script>

<style lang="stylus" scoped>

</style>
