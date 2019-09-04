<template>
  <div class="m-topBar">
    <div class="barLeft">
      <m-city></m-city>
      <m-user></m-user>
    </div>
    <div class="barRight">
      <m-nav></m-nav>
    </div>
  </div>
</template>

<script>
  import City from './city'
  import Nav from './nav'
  import User from './user'
  export default {
    name: 'index',
    components: {
      'm-city': City,
      'm-nav': Nav,
      'm-user': User
    }
  }
</script>

<style scoped lang="scss">
  .m-topBar{
    height: 40px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    background-color: rgb(248,248,248);
    padding: 0 36px;
    .barLeft {
      display: flex;
      align-items: center;
    }
  }
</style>