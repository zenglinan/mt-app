<template>
  <div class="m-login">
    <div class="hello">
      <img src="/img/avatar.jpg" alt="">
      <p>Hi! 你好</p>
    </div>
    <nuxt-link to="#" class="login login-in">
      注册
    </nuxt-link>
    <nuxt-link to="#" class="login sign-in">
      立即登录
    </nuxt-link>
  </div>
</template>

<script>
  export default {
    name: 'login'
  }
</script>

<style scoped lang="scss">
  .m-login {
    background-color: #fff;
    border: 1px solid #e5e5e5;
    width: 230px;
    height: 240px;

    .hello {
      padding-top: 30px;
      text-align: center;

      img {
        width: 47px;
        height: 47px;
        border-radius: 50%;
        border: 4px solid #E5E5E5;
      }

      p {
        font-size: 16px;
        color: #222;
        text-align: center;
        font-weight: 500;
        white-space: nowrap;
      }
    }
    a.login{
      cursor: pointer;
      width: 118px;
      text-align: center;
      margin: 10px auto 15px auto;
      background: #fff;
      border: 1px solid #e5e5e5;
      border-radius: 40px;
      font-size: 14px;
      color: #333;
      transition: background-color 0.3s;
      display: block;
      line-height: 38px;
      &:hover{
        background-color: #f6f6f6;
      }
    }
  }

</style>