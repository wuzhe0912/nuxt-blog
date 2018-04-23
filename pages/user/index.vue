<template lang="pug">
  div
    input(type="text" v-model="userId")
    button(@click="onLoadUser") Load User
</template>

<script>
export default {
  data() {
    return {
      userId:''
    }
  },
  methods: {
    onLoadUser() {
      this.$router.push('/user/' + this.userId);
    }
  }
}
</script>
