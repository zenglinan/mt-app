<template>
  <div class="m-qr-code">
    <div class="qr-code">
      <img src="/img/download-qr.png" alt="qr-code">
    </div>
    <h3>美团APP手机版</h3>
    <p><span>一元起</span>吃喝玩乐</p>
  </div>
</template>

<script>
  export default {
    name: 'download'
  }
</script>

<style scoped lang="scss">
  .m-qr-code {
    width: 228px;
    height: 165px;
    margin-top: 10px;
    background-color: #fff;
    border: 1px solid #e5e5e5;
    text-align: center;
    .qr-code{
      padding-top: 10px;
      text-align: center;
      img{
        vertical-align: top;
        width: 95px;
        height: 95px;
      }
    }
    h3 {
      font-size: 16px;
      color: #222222;
      font-weight: 500;
    }
    p {
      color: #3f3f3f;
      font-size: 12px;
      span{
        color: #EC5330;
        margin-right: 5px;
      }
    }
  }
</style>