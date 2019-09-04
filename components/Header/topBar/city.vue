<template>
  <div class="m-city">
    <div class="city">
      <svg class="icon" aria-hidden="true">
        <use xlink:href="#i-location"></use>
      </svg>
      <span>广州</span>
    </div>
    <div class="changeCity">
      <nuxt-link to="#" class="hoverable">切换城市</nuxt-link>
    </div>
    <div class="otherCity">
      <div>[</div>
      <div class="hoverable">佛山</div>
      <div class="hoverable">顺德</div>
      <div class="hoverable">南沙</div>
      <div>]</div>
    </div>
  </div>
</template>

<script>
  if (process.client) {
    require('@/assets/icon')
  }
  export default {
    name: 'city'
  }
</script>

<style scoped lang="scss">
  .m-city {
    display: inline-flex;
    align-items: center;

    .city {
      svg {
        width: 1.2em;
        height: 1.2em;
        fill: rgb(153, 153, 153);
      }
    }
    .changeCity{
      margin: 0 4px;
      padding: 0 2px;
      border: 1px solid #E5E5E5;
      border-radius: 2px;
    }
    .otherCity{
      display: flex;
      align-items: center;
      color: #999;
      .hoverable {
        margin: 0 4px;
      }
    }
  }
</style>