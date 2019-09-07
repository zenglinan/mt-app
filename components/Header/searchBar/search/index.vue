<template>
  <div class="m-search">
    <div class="search-top">
      <m-search-input></m-search-input>
      <m-recommand></m-recommand>
    </div>
    <m-link></m-link>
  </div>
</template>

<script>
  if (process.client) {
    require('@/assets/icon')
  }
  import searchInput from './searchInput'
  import recommand from './recommand'
  import link from './link'
  export default {
    name: 'search',
    components: {
      'm-search-input': searchInput,
      'm-recommand': recommand,
      'm-link': link
    }
  }
</script>

<style scoped lang="scss">
  .m-search {
    width: 550px;
    display: flex;
    flex-direction: column;
    align-items: center;
    color: #999;
    padding-top: 28px;
    margin: 0 auto;
  }
</style>