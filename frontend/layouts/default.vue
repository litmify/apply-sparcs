<template>
  <nuxt />
</template>

<style>
@import '~/assets/fonts/NanumBarunRoboto/stylesheet.css';

html {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}
</style>

<script>
export default {
  mounted() {
    this.intervalId = setInterval(() => {
      this.$store.commit('updateTime');
    }, 1000);
  },

  destroyed() {
    if (this.intervalId) {
      clearInterval(this.intervalId);
    }
  }
};
</script>
