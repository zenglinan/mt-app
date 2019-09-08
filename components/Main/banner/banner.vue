<template>
  <div class="m-banner">
    <div class="banner-top">
      <div class="carousel">
        <el-carousel :interval="5000" height="240px" indicator-position="none" arrow="always">
          <el-carousel-item v-for="(src, idx) in carousel" :key="idx">
            <img :src="src" alt="">
          </el-carousel-item>
        </el-carousel>
      </div>
      <div class="images">
        <img src="/img/banner6.jpg" alt="" style="width: 150px; height: 240px;">
      </div>
      <m-login></m-login>
    </div>
    <div class="banner-bottom">
      <div class="images"><img src="/img/banner7.png" alt="" style="width: 270px; height: 165px;"></div>
      <div class="images"><img src="/img/banner8.jpg" alt="" style="width: 270px; height: 165px;"></div>
      <div class="images"><img src="/img/banner9.jpg" alt="" style="width: 150px; height: 165px;"></div>
      <qr-code></qr-code>
    </div>
  </div>
</template>

<script>
  import carousel from '../carouselData'
  import login from './login'
  import qrCode from './qrCode'
  export default {
    name: 'banner',
    data() {
      return {
        carousel,
        banner: [
          '/img/banner7.png',
          '/img/banner8.jpg',
          '/img/banner9.jpg'
        ]
      }
    },
    components:{
      'm-login': login,
      qrCode
    }
  }
</script>

<style scoped lang="scss">
  img {
    display: block;
    vertical-align: top;
  }

  .carousel {
    width: 550px;

    .el-carousel {
      img {
        width: 550px;
        height: 240px;
      }
    }
  }

  .m-banner {
    padding: 12px 12px 0;

    .banner-top {
      display: flex;

      .images {
        margin: 0 10px;
      }

    }

    .banner-bottom {
      display: flex;
      align-items: center;

      .images {
        margin: 10px 10px 0 0;

        img {
          width: 270px;
          height: 165px;
        }

        &:last-child {
          img {
            width: 400px;
          }
        }
      }

    }
  }


</style>