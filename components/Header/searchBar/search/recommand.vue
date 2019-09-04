<template>
  <div class="m-recommand">
    <div class="recommandItem hoverable">广州长隆水上乐园</div>
    <div class="recommandItem hoverable">广州长隆欢乐世界</div>
    <div class="recommandItem hoverable">广州融创雪世界</div>
    <div class="recommandItem hoverable">广州长隆野生动物世界</div>
    <div class="recommandItem hoverable">珠江夜游</div>
  </div>
</template>

<script>
  export default {
    name: 'recommand'
  }
</script>

<style scoped lang="scss">
  .m-recommand{
    display: flex;
    padding: 8px 0 0 12px;
    .recommandItem {
      margin-right: 10px;
    }
  }
</style>