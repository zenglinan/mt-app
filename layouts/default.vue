<template>
  <el-container>
    <el-header>
      <m-header></m-header>
    </el-header>
    <el-main>
      <nuxt/>
    </el-main>
    <el-footer>Footer</el-footer>
  </el-container>
</template>
<script>
  import header from '@/components/Header/index'

  export default {
    components: {
      'm-header': header
    }
  }
</script>
<style>
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
  }

  .icon {
    width: 1em; height: 1em;
    vertical-align: -0.15em;
    fill: currentColor;
    overflow: hidden;
  }
</style>
