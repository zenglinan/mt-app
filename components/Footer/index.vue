<template>
  <div class="m-footer">
    <m-city-nav></m-city-nav>
    <m-relate-link></m-relate-link>
  </div>
</template>

<script>
  import cityNav from './cityNav'
  import relateLink from './relateLink'
  export default {
    name: 'index',
    components: {
      'm-city-nav': cityNav,
      'm-relate-link': relateLink
    }
  }
</script>

<style scoped lang="scss">
  .m-footer {
    margin: 0 36px;
  }

</style>