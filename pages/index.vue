<template lang="pug">
  section.wrap
    .title-container
      h1.title-txt Activello
      i.subTitle-txt just blog site
    .post-container
      PostPreview(
        v-for="node in postList",
        :key="node.id",
        :title="node.title",
        :summary="node.summary",
        :content="node.content",
        :imgUrl="node.imgUrl",
        :id="node.id"
      )
</template>

<script>
import PostPreview from '@/components/Blog/PostPreview'

export default {
  components: {
    PostPreview
  },

  asyncData (context) {
    return context.app.$storyapi.get('cdn/stories', {
      version: 'draft',
      starts_with: 'blog/'
    }).then((res) => {
      return {
        postList: res.data.stories.map((node) => {
          return {
            id: node.content._uid,
            title: node.content.title,
            summary: node.content.summary,
            content: node.content.content,
            imgUrl: node.content.image
          }
        })
      }
    })
  }
}
</script>

<style lang="scss" scoped>
  @import "./style";
</style>
