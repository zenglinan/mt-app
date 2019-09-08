<template>
  <div class="m-main">
    <m-menu></m-menu>
    <m-banner></m-banner>
  </div>
</template>

<script>
  import menu from './menu'
  import banner from './banner/banner'
  export default {
    name: 'm-main',
    components:{
      'm-menu': menu,
      'm-banner': banner
    }
  }
</script>

<style scoped lang="scss">
  .m-main{
    display: flex;
    align-items: flex-start;
  }
</style>