<template>
  <div class="m-searchInput">
    <input type="text" placeholder="搜索商家或地点">
    <button class="search">
      <svg class="icon" aria-hidden="true">
        <use xlink:href="#i-search"></use>
      </svg>
    </button>
  </div>

</template>

<script>
  export default {
    name: 'searchInput'
  }
</script>

<style scoped lang="scss">
  .m-searchInput {
    height: 40px;
    width: 550px;
    display: flex;
    align-items: center;

    input {
      font-size: 14px;
      height: 100%;
      width: 85.45%;
      line-height: 100%;
      padding: 15px;
      border-radius: 4px 0 0 4px;
      background: transparent;
      border: 1px solid #E5E5E5;
      &::placeholder {
        color: #999;
      }
    }

    button.search {
      box-sizing: border-box;
      line-height: 100%;
      height: 100%;
      background: #FFC300;
      color: #222222;
      cursor: pointer;
      width: 14.55%;
      margin-left: -1px;
      border-radius: 0 4px 4px 0;
      svg {
        height: 20px;
        width: 20px;
      }
    }
  }


</style>