<template>
  <div class="m-banner">
    <div class="banner-top">
      <div class="carousel">

        <el-carousel :interval="5000000" height="220px" indicator-position="none" arrow="always">
          <el-carousel-item v-for="(src, idx) in banner" :key="idx"><img :src="src" alt=""></el-carousel-item>
        </el-carousel>
      </div>
      <div class="carousel">

      </div>
    </div>
  </div>
</template>

<script>
  import banner from './bannerData'

  export default {
    name: 'banner',
    data() {
      return {
        banner
      }
    }
  }
</script>

<style scoped lang="scss">
  .carousel {
    width: 550px;
    .el-carousel {
      img {
        width: 550px;
        height: 220px;
      }
    }
  }
  .m-banner {
    padding: 12px;
  }


</style>