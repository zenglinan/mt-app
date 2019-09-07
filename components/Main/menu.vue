<template>
  <el-container class="m-menu">
    <el-aside style="width: 228px;">
      <el-menu>
        <h3>全部分类</h3>
        <el-menu-item v-for="(item, idx) in menu" :key="idx">
          <i :class="item.type"></i>{{item.name}}<span class="arrow"/>
        </el-menu-item>
      </el-menu>
    </el-aside>
    <el-container class="card" v-show="onShow">
      <el-main>
        <template v-for="item in menu" v-show="">
          <dl v-for="(child, idx) in item.child" :key="idx">
            <dt>{{child.title}}</dt>
            <dd v-for="(childContent, idx) in child.child" :key="idx">{{childContent}}</dd>
          </dl>
        </template>

      </el-main>
    </el-container>
  </el-container>
</template>

<script>
  import menu from './menuData'

  export default {
    name: 'index',
    data() {
      return {
        menu,
        hasEnterMenu: false
      }
    },
    computed: {
      onShow(){
        return this.hasEnterMenu
      }
    }
  }
</script>

<style scoped lang="scss">
  @import "@/assets/scss/fontClass.scss";

  .m-menu {
    .el-aside {
      width: 230px;
      border: 1px solid #E5E5E5;

      h3 {
        padding: 15px 0 20px 15px;
      }

      .el-menu-item {
        cursor: default;
        padding: 3px 12px;
        height: auto;
        line-height: normal;
        color: #646464;
        transition: none;

        &:hover {
          background: rgba(255, 150, 0, 0.08);
          font-weight: bold;
          color: #222;
        }
      }
    }

    .card {
      width: 400px;
      height: 416px;
      flex-grow: 0;

      .el-main {
        padding: 20px 30px;
      }
    }
  }

</style>