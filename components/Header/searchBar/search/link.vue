<template>
  <ul class="m-link">
      <li><nuxt-link to="#">美团外卖</nuxt-link></li>
      <li><nuxt-link to="#">猫眼电影</nuxt-link></li>
      <li><nuxt-link to="#">美团酒店</nuxt-link></li>
      <li><nuxt-link to="#">名宿 / 公寓</nuxt-link></li>
      <li><nuxt-link to="#">商家入驻</nuxt-link></li>
      <li><nuxt-link to="#">美团公益</nuxt-link></li>
  </ul>
</template>

<script>
  export default {
    name: 'm-link'
  }
</script>

<style scoped lang="scss">
.m-link {padding: 30px 0 20px 0;display: flex;
  li {padding: 0 22px;color: #222;font-weight: bold;font-size: 16px;
    a {white-space: nowrap;}
    &:nth-child(1){
      &:hover{color: #fbd700;}
    }
    &:nth-child(2){
      &:hover{color: #ed1e24;}
    }
    &:nth-child(3){
      &:hover{color: #f04d4e;}
    }
    &:nth-child(4){
      &:hover{color: #fdc411;}
    }
    &:nth-child(5){
      &:hover{color: #fe8c00;}
    }
    &:nth-child(6){
      &:hover{color: #f04d4e;}
    }
  }
}
</style>