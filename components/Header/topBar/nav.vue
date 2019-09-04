<template>
  <div class="m-nav">
    <div class="navItem hoverable">我的美团</div>
    <div class="navItem hoverable">手机APP</div>
    <div class="navItem hoverable">商家中心</div>
    <div class="navItem hoverable">美团规则</div>
    <div class="navItem hoverable">网站导航</div>
  </div>
</template>

<script>
  export default {
    name: 'navigation'
  }
</script>

<style scoped lang="scss">
.m-nav{
  display: flex;
  align-items: center;
  .navItem {
    height: 40px;
    padding: 12px 14px;
    &:hover {
      background-color: #fff;
      border-color: #E5E5E5;
      box-shadow: 0 3px 5px 0 rgba(0,0,0,0.1);
    }
  }
}
</style>