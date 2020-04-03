<template lang="pug">
  .preview-wrap
    nuxt-link(
      :to="id"
    )
      article.post-preview
        .preview-title
          span {{ title }}
        .preview-img
          img(:src="imgUrl")
        .preview-text
          span {{ summary }}
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    summary: {
      type: String,
      required: true
    },
    content: {
      type: String,
      required: true
    },
    imgUrl: {
      type: String,
      required: true
    },
    id: {
      type: String,
      required: true
    }
  },

  data () {
    return {}
  }
}
</script>

<style lang="scss" scoped>
  @import "./style";
</style>
