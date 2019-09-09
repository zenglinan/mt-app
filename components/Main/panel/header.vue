<template>
  <header class="panel-header">
    <div class="headerLeft">
      <h3>{{data.title}}</h3>
      <ul class="childTitle">
        <li v-for="(title,idx) in data.child" :key="idx"
            @mouseenter="changeCurrent(idx)"
        >
          {{title}}
          <div class="arrow" v-show="onShow(idx)"></div>
        </li>
      </ul>
    </div>
    <span v-if="data.hasMore" class="headerRight">
      <nuxt-link to="#">
        全部 >
      </nuxt-link>
    </span>
  </header>
</template>

<script>
  export default {
    name: 'panel-header',
    props: {
      data: {
        type: Object,
        default: {},
        validator(data) {
          return data.hasOwnProperty('title') && data.hasOwnProperty('child')
        }
      }
    },
    data() {
      return {
        selected: undefined
      }
    },
    inject: ['eventBus'],
    mounted() {
      this.eventBus.$on('assignSelected', (idx) => {
        this.selected = idx
      })
    },
    computed: {
      onShow() {
        const _this = this
        return function(idx) {
          return idx === _this.selected
        }
      }
    },
    methods: {
      changeCurrent(idx) {
        this.eventBus.$emit('changeSelected', idx)
      }
    }
  }
</script>

<style scoped lang="scss">
  .panel-header {
    border-radius: 5px 5px 0 0;
    display: flex;
    height: 44px;
    line-height: 44px;
    align-items: center;
    justify-content: space-between;
    font-size: 14px;
    color: #fff;

    .headerLeft {
      display: flex;
      align-items: center;

      h3 {
        font-size: 18px;
        margin: 0 10px 0 13px;
        font-family: "MFShangHei-Regular";
      }

      ul.childTitle {
        display: flex;
        align-items: center;

        li {
          position: relative;
          padding: 0 5px;
          cursor: pointer;

          .arrow {
            position: absolute;
            bottom: 0px;
            left: 50%;
            transform: translateX(-50%);
            height: 0;
            border: 6px solid transparent;
            border-top: none;
            border-bottom-color: #fff;
          }
        }
      }
    }

    .headerRight {
      margin-right: 20px;
    }
  }
</style>