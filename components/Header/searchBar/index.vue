<template>
  <div class="m-searchBar">
    <m-logo></m-logo>
    <m-search></m-search>
  </div>
</template>

<script>
  import Logo from './logo'
  import Search from './search/index'
  export default {
    name: 'index',
    components: {
      'm-logo': Logo,
      'm-search': Search
    }
  }
</script>

<style scoped lang="scss">
  .m-searchBar{
    display: flex;
  }
</style>