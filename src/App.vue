<template>
  <div id="app">
      <HeaderTop/>
      <MainCenter/>
      <FooterBottom/>
  </div>
</template>

<script>
import HeaderTop from '@/components/HeaderTop.vue';
import MainCenter from '@/components/MainCenter.vue';
import FooterBottom from '@/components/FooterBottom.vue';

export default {
  name: 'App',
  components: {
    HeaderTop,
    FooterBottom,
    MainCenter
  }
}
</script>

<style lang="scss">
@import '@/assets/style/common.scss';

#app {
  font-family: 'Work Sans', sans-serif;
  -webkit-font-smoothing: antialiased;
}
</style>
