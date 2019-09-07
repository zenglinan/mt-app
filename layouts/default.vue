<template>
  <div class="container">
    <header>
      <m-header></m-header>
    </header>
    <main class="main">
      <nuxt/>
    </main>
    <footer class="footer">Footer</footer>
  </div>
</template>
<script>
  import header from '@/components/Header/index'

  export default {
    components: {
      'm-header': header
    }
  }
</script>
<style lang="scss" scoped>
  html {
    font-family: "-apple-system","BlinkMacSystemFont","Roboto","Helvetica Neue","MIcrosoft YaHei",sans-serif !important;
    font-size: 16px;
    word-spacing: 1px;
    -ms-text-size-adjust: 100%;
    -webkit-text-size-adjust: 100%;
    -moz-osx-font-smoothing: grayscale;
    -webkit-font-smoothing: antialiased;
    box-sizing: border-box;
  }

  .el-header {
    padding: 0;
    height: auto !important;
    position: relative;
    z-index: 10;
  }
  .el-main {
    padding: 0;
    position: relative;
    z-index: 99;
  }
  .icon {
    width: 1em; height: 1em;
    vertical-align: -0.15em;
    fill: currentColor;
    overflow: hidden;
  }
</style>
