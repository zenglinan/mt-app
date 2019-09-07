<template>
  <header class="m-header">
    <m-top-bar></m-top-bar>
    <m-search-bar></m-search-bar>
  </header>
</template>

<script>
  import topBar from "./topBar/index"
  import searchBar from "./searchBar/index"
  export default {
    name: 'index',
    components: {
      'm-top-bar': topBar,
      'm-search-bar': searchBar,
    }
  }
</script>

<style scoped lang="scss">
  .m-header{
    font-size: 12px;
    color: #666;
    background: #fff;
    box-shadow: 0 10px 27px 0 rgba(0,0,0,0.10);
  }
</style>