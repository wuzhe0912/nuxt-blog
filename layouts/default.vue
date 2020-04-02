<template lang="pug">
  .layout
    Header
    main.main-content
      nuxt
</template>

<script>
import Header from '@/components/Header'

export default {
  components: {
    Header
  },
  data () {
    return {}
  }
}
</script>

<style lang="scss" scoped>

</style>
