<template>
  <div class="m-main">
    <div class="banner-container">
      <m-menu></m-menu>
      <m-banner></m-banner>
    </div>
    <div class="scenes-container">
      <m-panel :selected.sync="selected1">
        <m-panel-header :data="data" style="background-color: rgb(254,97,70)"></m-panel-header>
        <m-panel-main v-for="(part, idx) in detail1" :key="idx" :id="idx">
          <m-panel-card v-for="(item,idx) in part" :key="idx" :detail="item">
          </m-panel-card>
        </m-panel-main>
      </m-panel>
    </div>
  </div>
</template>

<script>
  import menu from './menu'
  import banner from './banner/index'
  import panel from './panel/index'
  import panelHeader from './panel/header'
  import panelMain from './panel/main'
  import panelCard from './panel/card'

  export default {
    name: 'm-main',
    data() {
      return {
        selected1: 0,
        data: {
          title: '有格调',
          child: ['全部', '约会聚餐', '丽人SPA', '电影演出', '品质出游'],
          hasMore: true
        },
        detail1: [
          [{
            title: '牛小灶牛腩牛杂煲（江南西人直营店）',
            description: '牛腩牛杂煲套餐，建议2人使用',
            img: {
              src: '//p0.meituan.net/msmerchant/f1dc5500c3659b1cc206c1c21be1b6a7307367.jpg@552w_312h_1e_1c',
              width: '369px',
              height: '208px'
            },
            price: '129'
          },
            {
              title: '牛小灶牛腩牛杂煲（江南西人直营店）',
              description: '牛腩牛杂煲套餐，建议2人使用',
              img: {
                src: '//p0.meituan.net/msmerchant/f1dc5500c3659b1cc206c1c21be1b6a7307367.jpg@552w_312h_1e_1c',
                width: '369px',
                height: '208px'
              },
              price: '129'
            }],

          [{
            title: '牛小灶牛腩牛杂煲（江南西人直营店）',
            description: '牛腩牛杂煲套餐，建议2人使用',
            img: {
              src: '//p1.meituan.net/msmerchant/772095c895dabfeb2cfaf493e653e6412087751.jpg@552w_312h_1e_1c',
              width: '369px',
              height: '208px'
            },
            price: '129'
          },
            {
              title: '牛小灶牛腩牛杂煲（江南西人直营店）',
              description: '牛腩牛杂煲套餐，建议2人使用',
              img: {
                src: '//p1.meituan.net/msmerchant/772095c895dabfeb2cfaf493e653e6412087751.jpg@552w_312h_1e_1c',
                width: '369px',
                height: '208px'
              },
              price: '129'
            }],

          [{
            title: '牛小灶牛腩牛杂煲（江南西人直营店）',
            description: '牛腩牛杂煲套餐，建议2人使用',
            img: {
              src: '//p0.meituan.net/msmerchant/f1dc5500c3659b1cc206c1c21be1b6a7307367.jpg@552w_312h_1e_1c',
              width: '369px',
              height: '208px'
            },
            price: '129'
          },
            {
              title: '牛小灶牛腩牛杂煲（江南西人直营店）',
              description: '牛腩牛杂煲套餐，建议2人使用',
              img: {
                src: '//p0.meituan.net/msmerchant/f1dc5500c3659b1cc206c1c21be1b6a7307367.jpg@552w_312h_1e_1c',
                width: '369px',
                height: '208px'
              },
              price: '129'
            }],

          [{
            title: '牛小灶牛腩牛杂煲（江南西人直营店）',
            description: '牛腩牛杂煲套餐，建议2人使用',
            img: {
              src: '//p1.meituan.net/msmerchant/772095c895dabfeb2cfaf493e653e6412087751.jpg@552w_312h_1e_1c',
              width: '369px',
              height: '208px'
            },
            price: '129'
          },
            {
              title: '牛小灶牛腩牛杂煲（江南西人直营店）',
              description: '牛腩牛杂煲套餐，建议2人使用',
              img: {
                src: '//p1.meituan.net/msmerchant/772095c895dabfeb2cfaf493e653e6412087751.jpg@552w_312h_1e_1c',
                width: '369px',
                height: '208px'
              },
              price: '129'
            }],

          [{
            title: '牛小灶牛腩牛杂煲（江南西人直营店）',
            description: '牛腩牛杂煲套餐，建议2人使用',
            img: {
              src: '//p0.meituan.net/msmerchant/f1dc5500c3659b1cc206c1c21be1b6a7307367.jpg@552w_312h_1e_1c',
              width: '369px',
              height: '208px'
            },
            price: '129'
          },
            {
              title: '牛小灶牛腩牛杂煲（江南西人直营店）',
              description: '牛腩牛杂煲套餐，建议2人使用',
              img: {
                src: '//p0.meituan.net/msmerchant/f1dc5500c3659b1cc206c1c21be1b6a7307367.jpg@552w_312h_1e_1c',
                width: '369px',
                height: '208px'
              },
              price: '129'
            }]
        ]
      }
    },
    components: {
      'm-menu': menu,
      'm-banner': banner,
      'm-panel': panel,
      'm-panel-header': panelHeader,
      'm-panel-main': panelMain,
      'm-panel-card': panelCard
    }
  }
</script>

<style scoped lang="scss">
  .m-main {
    padding: 0 36px;

    .banner-container {
      display: flex;
      align-items: flex-start;
    }
  }
</style>