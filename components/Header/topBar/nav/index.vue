<template>
  <div class="m-nav">
    <ul class="navList" ref="navList">
      <li class="nav" v-for="(item,index) in navData" :key="index">
        <nuxt-link class="navItem hoverable" to="#"
                   :class="{isLeaf: !item.list}"
        >
          {{item.title}}
        </nuxt-link>
        <dl class="hidden">
          <dd v-for="(list,index) in item.list" :key="index">
            <nuxt-link class="hoverable" to="#">{{list}}</nuxt-link>
          </dd>
        </dl>
      </li>
      <li class="nav">
        <nuxt-link class="navItem hoverable" to="#">网站导航</nuxt-link>
        <div class="card hidden">
          <div class="contentItem" v-for="(data, index) in cardData" :key="index">
            <dl>
              <dt>{{data.title}}</dt>
              <dd v-for="(listItem, index) in data.list" :key="index">
                <nuxt-link class="hoverable" to="#">{{listItem}}</nuxt-link>
              </dd>

            </dl>
          </div>
          <div class="contentItem">
            <dl>
              <dt>手机应用</dt>
              <dd v-for="(img, index) in images" :key="index">
                <nuxt-link to="#"><img :src="img.src" :alt="img.alt"></nuxt-link>
              </dd>
            </dl>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
  import card from './card'
  import { images, cardData, navData } from './data'

  export default {
    name: 'navigation',
    data() {
      return {
        images,
        cardData,
        navData
      }
    },
    components: {
      'm-card': card
    },
    mounted() {
      const navItem = this.$refs.navList.querySelectorAll('.navItem')
      for (let i = 0, len = navItem.length; i < len; i++) {
        const item = navItem[i]
        const list = item.nextElementSibling
        const listClasses = list.classList
        const itemClasses = item.classList
        if (itemClasses.contains('isLeaf')) continue
        this.bindEvents({item, list, listClasses, itemClasses})
      }
    },
    methods: {
      hide(itemClasses, listClasses) {
        itemClasses.remove('active')
        listClasses.add('hidden')
      },
      show(itemClasses, listClasses) {
        itemClasses.add('active')
        listClasses.remove('hidden')
      },
      bindEvents({item, list, listClasses, itemClasses}){
        item.addEventListener('mouseenter', () => {
          this.show(itemClasses, listClasses)
        })
        item.addEventListener('mouseleave', () => {
          let timer = setTimeout(() => {
            this.hide(itemClasses, listClasses)
          }, 10)
          list.addEventListener('mouseenter', () => {
            clearTimeout(timer)
          })
          list.addEventListener('mouseleave', () => {
            this.hide(itemClasses, listClasses)
          })
        })
      }
    }
  }
</script>

<style scoped lang="scss">
  .m-nav {display: flex;align-items: center;

    ul.navList {display: flex;

      li.nav {list-style: none;position: relative;height: 40px;

        .card {width: 1200px;position: absolute;top: 40px;
          right: 0;background-color: #fff;border-color: #E5E5E5;
          box-shadow: 0 3px 5px 0 rgba(0, 0, 0, 0.1);
          padding: 30px 36px 36px 47px;display: flex;z-index: 2;

          .contentItem:nth-child(1) {
            dl {width: 247px;}

            dd {width: 33%;}
          }

          .contentItem:nth-child(2) {
            dl {width: 156px;}

            dd {width: 50%;}
          }

          .contentItem:nth-child(3) {
            margin-right: 84px;

            dl {width: 90px;}

            dd {width: 100%;}
          }

          .contentItem:nth-child(4) {
            dl {margin-right: 0;display: flex;justify-content: space-between;}

            dd {
              img {width: 60px;height: 60px;}
            }
          }

          .contentItem {
            margin-right: 47px;

            dl {display: flex;flex-wrap: wrap;

              dt {text-align: center;width: 100%;margin-bottom: 26px;
                font-size: 14px;color: #222222;font-weight: 500;
              }

              dd {padding: 5px 0;text-align: center;}
            }
          }
        }

        .navItem {display: block;height: 40px;line-height: 40px;padding: 0 14px;

          &.active {background-color: #fff;border-color: #E5E5E5;
            box-shadow: 0 3px 5px 0 rgba(0, 0, 0, 0.1);
          }
        }

        &:not(:nth-child(5)) {
          dl {position: absolute;z-index: 2;width: 100%;top: 40px;
            right: 0;background-color: #fff;border-color: #E5E5E5;
            box-shadow: 0 3px 5px 0 rgba(0, 0, 0, 0.1);

            dd {text-align: center;padding: 12px 10px;}
          }
        }

        &:nth-child(3) {
          dl {width: 150%;

            dd {padding: 12px 6px;}
          }
        }

        &:nth-child(5) {position: relative;}
      }
    }

  }
</style>