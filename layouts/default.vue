<template lang="pug">
  .layout
    .layout-container
      Header
      main.main-content
        nuxt
    Footer
</template>

<script>
import Header from '@/components/Header'
import Footer from '@/components/Footer'

export default {
  components: {
    Header,
    Footer
  },
  data () {
    return {}
  }
}
</script>

<style lang="scss" scoped>
  @import '@/assets/scss/share.scss';
  .layout-container {
    min-height: calc(100vh - #{to-rem(70px)});
  }
</style>
