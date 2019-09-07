<template>
  <div class="m-searchInput">
    <input type="text" placeholder="搜索商家或地点"
           v-model="input"
           @focus="onFocus"
           @blur="onBlur"
    >
    <dl class="recommand content" v-show="showRecommand">
      <dt>热门推荐</dt>
      <dd v-for="(data, idx) in recommandData" :key="idx">
        <nuxt-link to="#" class="hoverable">{{data}}</nuxt-link>
      </dd>
    </dl>
    <dl class="search content" v-show="showSearch">
      <dd v-for="(data, idx) in searchData" :key="idx" class="hoverable">
        <nuxt-link to="#">{{data}}</nuxt-link>
      </dd>
    </dl>
    <button class="search">
      <svg class="icon" aria-hidden="true">
        <use xlink:href="#i-search"></use>
      </svg>
    </button>
  </div>

</template>

<script>
  export default {
    name: 'searchInput',
    data() {
      return {
        focus: false,
        input: '',
        recommandData: [
          '广州长隆野生动物世界',
          '广州长隆欢乐世界',
          '广州长隆水上乐园'
        ],
        searchData: [
          '大盘鸡',
          '烩面',
          '火锅'
        ]
      }
    },
    computed: {
      showRecommand() {
        return this.focus && !this.input
      },
      showSearch() {
        return this.focus && this.input
      }
    },
    methods: {
      onFocus() {
        this.focus = true
      },
      onBlur() {
        this.focus = false
      }
    }
  }
</script>

<style scoped lang="scss">
  .m-searchInput {height: 40px;width: 550px;display: flex;
    align-items: center;position: relative;

    input {font-size: 14px;height: 100%;width: 85.45%;
      line-height: 100%;padding: 15px;border-radius: 4px 0 0 4px;
      background: transparent;border: 1px solid #E5E5E5;

      &::placeholder {color: #999;}
    }

    dl.content {position: absolute;top: 40px;left: 0;
      width: 85.45%;border: 1px solid #E5E5E5;background-color: #fff;
      z-index: 10;box-shadow: 0 3px 5px 0 rgba(0, 0, 0, 0.1);
      border-radius: 2px;transform: translateY(-1px);

      dt {font-weight: bold;padding-bottom: 6px;width: 100%;}

      &.recommand {display: flex;flex-wrap: wrap;padding: 10px;

        dd {padding-right: 10px;}
      }

      &.search {
        dd {cursor: pointer;padding: 8px 10px;color: #666;

          &:hover {background-color: rgb(248, 248, 248);}

          a {color: inherit;}
        }
      }
    }

    button.search {box-sizing: border-box;line-height: 100%;
      height: 100%;background: #FFC300;color: #222222;
      cursor: pointer;width: 14.55%;margin-left: -1px;
      border-radius: 0 4px 4px 0;

      svg {height: 20px;width: 20px;}
    }
  }


</style>