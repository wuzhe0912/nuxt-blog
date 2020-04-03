<template lang="pug">
  header.main-header
    .logo
    nav.main-nav
      ul.nav-links
        nuxt-link.link-txt(to="/") Blog
        nuxt-link.link-txt(to="/weather") Weather
</template>

<script>
export default {
  data () {
    return {}
  }
}
</script>

<style lang="scss" scoped>
  @import './style';
</style>
