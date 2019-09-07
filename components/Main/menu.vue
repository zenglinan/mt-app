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
    <el-container class="card">
      <el-main>
        <template v-for="menuItem in menu" v-show="">
          <dl v-for="(childMenu, idx) in menuItem.child" :key="idx">
            <h3>{{childMenu.title}}</h3>
            <dd v-for="(content, id) in childMenu.child" :key="id">{{content}}</dd>
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
        inMenu: false
      }
    },
    computed: {
      onShow(){
        return this.inMenu
      }
    }
  }
</script>

<style scoped lang="scss">
  @import "@/assets/scss/fontClass.scss";

  .m-menu {
    transform: translateY(-50px);
    margin-left: 36px;
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