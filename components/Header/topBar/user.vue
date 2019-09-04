<template>
  <div class="m-user">
    <div class="login">立即登录</div>
    <div class="hoverable logout">注册</div>
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

    > div {
      margin-left: 10px;
    }

    .login {
      cursor: pointer;
      color: #fe8c00;
    }

  }
</style>