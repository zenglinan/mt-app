<template>
  <div class="m-logo">
    <img src="../../../static/img/logo.png" alt="美团网">
  </div>
</template>

<script>
  export default {
    name: 'logo'
  }
</script>

<style scoped lang="scss">
  .m-logo {
    position: absolute;
    left: 0;
    top: 28px;
    margin-left: 36px;
    img {
      float: left;
      width: 126px;
      height: 46px;
    }
  }
</style>