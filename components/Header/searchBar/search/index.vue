<template>
  <div class="m-search">
    <m-search-input></m-search-input>
    <m-recommand></m-recommand>
  </div>
</template>

<script>
  if (process.client) {
    require('@/assets/icon')
  }
  import searchInput from './searchInput'
  import recommand from './recommand'
  export default {
    name: 'search',
    components: {
      'm-search-input': searchInput,
      'm-recommand': recommand
    }
  }
</script>

<style scoped lang="scss">
  .m-search {

    padding-top: 28px;
    position: absolute;
    left: 50%;
    transform: translateX(-50%);


  }
</style>