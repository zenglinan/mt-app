<template>
  <div class="m-main">
    <m-menu></m-menu>
  </div>
</template>

<script>
  import menu from './menu'
  export default {
    name: 'm-main',
    components:{
      'm-menu': menu
    }
  }
</script>

<style scoped lang="scss">
  .m-main{}

</style>