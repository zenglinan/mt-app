<template>
  <div class="m-menu" @mouseleave="leave">
    <div style="width: 227px;" class="menuWrapper">
      <dl>
        <h3>全部分类</h3>
        <dd v-for="(item, idx) in menu" :key="idx"
            @mouseenter="enter(idx)">
          <i :class="item.type"></i>{{item.name}}<span class="arrow"/>
        </dd>
      </dl>
    </div>
    <div class="card" v-show="onShow" ref="card">
      <div class="detail" v-for="(item, idx) in menu[hoverIndex || 0].child" :key="idx">
        <h3>{{item.title}}</h3>
        <dl>
          <dd v-for="(t,idx) in item.child" :key="idx">
            {{t}}
          </dd>
        </dl>
      </div>
    </div>
  </div>
</template>

<script>
  import menu from './menuData'

  export default {
    name: 'index',
    data() {
      return {
        menu,
        hoverIndex: undefined
      }
    },
    methods: {
      enter(idx) {
        this.hoverIndex = idx
      },
      leave() {
          this.hoverIndex = undefined
      }
    },
    computed: {
      onShow() {
        return this.hoverIndex !== undefined
      }
    }
  }
</script>

<style scoped lang="scss">
  @import "@/assets/scss/fontClass.scss";

  .m-menu {
    font-family: 'meituan';
    flex-grow: 0;
    transform: translateY(-45px);
    box-sizing: border-box;
    position: relative;
    z-index: 99;

    .menuWrapper {
      background-color: #fff;
      border: 1px solid #E5E5E5;
      height: 472px;

      dl {
        border: none;
      }

      h3 {
        padding: 16px 0 20px 16px;
        height: 57px;
      }

      dd {
        cursor: default;
        height: auto;
        line-height: normal;
        color: #646464;
        transition: none;
        position: relative;
        padding: 4px 12px;
        font-size: 13px;

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
      background-color: #fff;
      position: absolute;
      left: 227px;
      top: 57px;
      z-index: 99;

    }
  }

  i {
    font-family: "meituan";
    font-size: 14px;
    font-style: normal;
    margin-right: 11px;

    &:before {
      width: 14px;
      height: 14px;
      display: inline-block;
    }
  }

  .arrow {
    width: 6px;
    height: 6px;
    color: #BFBFBF;
    border-bottom: 1px solid #BFBFBF;
    border-right: 1px solid #BFBFBF;
    transform: rotate(-45deg);
    display: block;
    position: absolute;
    right: 13px;
    top: 0;
    bottom: 0;
    margin: auto;
  }

</style>