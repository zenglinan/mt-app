<template>
  <div class="m-relate-link">
    <div class="column" v-for="(column, idx) in listData" :key="idx">
      <dl class="list" v-for="(list, idx) in column" :key="idx">
        <dt>{{list.title}}</dt>
        <dd v-for="(item, idx) in list.items" :key="idx">
          <nuxt-link to="#" class="hoverable">{{item}}</nuxt-link>
        </dd>
      </dl>
    </div>
  </div>
</template>

<script>
  import listData from './relateLinkData'
  export default {
    name: 'relateLink',
    data() {
      return {
        listData
      }
    }
  }
</script>

<style scoped lang="scss">
  .m-relate-link{
    border-top: 1px solid #e5e5e5;
    display: flex;
    padding: 40px 45px;
    .column{
      width: 20%;
      dl.list{
        padding-bottom: 30px;
        dt{
          color: #333;
          font-size: 14px;
          padding: 6px 0;
        }
        dd{
          font-size: 12px;
          color: #666;
          padding: 4px 0;
        }
      }
    }
  }

</style>