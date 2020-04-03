<template lang="pug">
  .post-wrap
    .post-img
      img(:src="image")
    .post-container
      h2.post-title {{ title }}
      .post-content(v-html="content")
</template>

<script>
import marked from 'marked'

export default {
  asyncData (context) {
    return context.app.$storyapi.get(`cdn/stories/blog/${context.params.postId}`, {
      version: 'draft'
    }).then((res) => {
      return {
        image: res.data.story.content.image,
        title: res.data.story.content.title,
        content: marked(res.data.story.content.content)
      }
    })
  }
}
</script>

<style lang="scss" scoped>
  @import "./style";
</style>
