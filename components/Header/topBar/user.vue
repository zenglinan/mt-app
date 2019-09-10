<template>
  <div class="m-user">
    <nuxt-link class="login" to="signIn">立即登录</nuxt-link>
    <nuxt-link class="hoverable logout" to="register">注册</nuxt-link>
  </div>
</template>

<script>
  export default {
    name: 'user'
  }
</script>

<style scoped lang="scss">
  .m-user {
    display: flex;
    align-items: center;
    margin-left: 15px;

    > a {
      margin-left: 10px;
    }

    .login {
      cursor: pointer;
      color: #fe8c00;
    }

  }
</style>