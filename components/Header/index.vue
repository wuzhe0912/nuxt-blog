<template lang="pug">
  header.main-header
    .logo
    nav.main-nav
      ul.nav-links
        nuxt-link.link-txt(to="/") Home
        nuxt-link.link-txt(to="/about") About
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
