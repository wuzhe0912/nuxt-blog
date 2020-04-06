<template lang="pug">
  .error-wrap
    .error-text 找不到這個頁面
    nuxt-link.btn(to="/") 回到首頁
</template>

<script>
export default {
  data () {
    return {}
  }
}
</script>

<style lang="scss" scoped>
  @import '@/assets/scss/share.scss';

  .error-wrap {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
    font-size: to-rem(40px);
    margin-top: to-rem(64px);
  }

  .btn {
    display: flex;
    justify-content: center;
    align-items: center;
    width: to-rem(200px);
    height: to-rem(60px);
    font-size: to-rem(28px);
    color: $light;
    margin-top: to-rem(24px);
    border: 1px solid $border-line;
    background: $header-bg;
    border-radius: to-rem(10px);
  }
</style>
