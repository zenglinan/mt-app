<template>
  <div class="m-nav">
    <ul class="navList" ref="navList">
      <li class="nav">
        <nuxt-link class="navItem hoverable" to="#">我的美团</nuxt-link>
        <dl class="hidden">
          <dd>
            <nuxt-link class="hoverable" to="#">我的订单</nuxt-link>
          </dd>
          <dd>
            <nuxt-link class="hoverable" to="#">我的收藏</nuxt-link>
          </dd>
          <dd>
            <nuxt-link class="hoverable" to="#">抵用券</nuxt-link>
          </dd>
          <dd>
            <nuxt-link class="hoverable" to="#">账户设置</nuxt-link>
          </dd>
        </dl>
      </li>
      <li class="nav">
        <nuxt-link class="navItem hoverable" to="#">手机APP</nuxt-link>
      </li>
      <li class="nav">
        <nuxt-link class="navItem hoverable" to="#">商家中心</nuxt-link>
        <dl class="hidden">
          <dd>
            <nuxt-link class="hoverable" to="#">登录商家中心</nuxt-link>
          </dd>
          <dd>
            <nuxt-link class="hoverable" to="#">美团智能收银</nuxt-link>
          </dd>
          <dd>
            <nuxt-link class="hoverable" to="#">我想合作</nuxt-link>
          </dd>
          <dd>
            <nuxt-link class="hoverable" to="#">手机免费开店</nuxt-link>
          </dd>
          <dd>
            <nuxt-link class="hoverable" to="#">餐饮代理商招募</nuxt-link>
          </dd>
          <dd>
            <nuxt-link class="hoverable" to="#">商家申请开票</nuxt-link>
          </dd>
          <dd>
            <nuxt-link class="hoverable" to="#">免费合作美团排队</nuxt-link>
          </dd>
        </dl>
      </li>
      <li class="nav">
        <nuxt-link class="navItem hoverable" to="#">美团规则</nuxt-link>
        <dl class="hidden">
          <dd>规则中心</dd>
          <dd>规则目录</dd>
          <dd>规则评议院</dd>
        </dl>
      </li>
      <li class="nav">
        <nuxt-link class="navItem hoverable" to="#">网站导航</nuxt-link>
        <div class="card hidden">
          <div class="contentItem">
            <dl>
              <dt>酒店旅游</dt>
              <dd class="hoverable">国际机票</dd>
              <dd class="hoverable">火车票</dd>
              <dd class="hoverable">榛果民宿</dd>
              <dd class="hoverable">经济型酒店</dd>
              <dd class="hoverable">主题酒店</dd>
              <dd class="hoverable">商务酒店</dd>
              <dd class="hoverable">公寓</dd>
              <dd class="hoverable">豪华酒店</dd>
              <dd class="hoverable">客栈</dd>
              <dd class="hoverable">青年旅社</dd>
              <dd class="hoverable">度假酒店</dd>
              <dd class="hoverable">别墅</dd>
              <dd class="hoverable">农家院</dd>
            </dl>
          </div>
          <div class="contentItem">
            <dl>
              <dt>吃美食</dt>
              <dd class="hoverable">烤鱼</dd>
              <dd class="hoverable">特色小吃</dd>
              <dd class="hoverable">烧烤</dd>
              <dd class="hoverable">自助餐</dd>
              <dd class="hoverable">火锅</dd>
              <dd class="hoverable">代金券</dd>
            </dl>
          </div>
          <div class="contentItem">
            <dl>
              <dt>看电影</dt>
              <dd class="hoverable">热映电影</dd>
              <dd class="hoverable">热门影院</dd>
              <dd class="hoverable">热映电影口碑榜</dd>
              <dd class="hoverable">最受期待电影</dd>
              <dd class="hoverable">国内票房榜</dd>
              <dd class="hoverable">北美票房榜</dd>
              <dd class="hoverable">电影排行榜</dd>
            </dl>
          </div>
          <div class="contentItem">
            <dl>
              <dt>手机应用</dt>
              <dd>
                <nuxt-link to="#"><img src="../../../../assets/img/meituan.png" alt=""></nuxt-link>
              </dd>
              <dd>
                <nuxt-link to="#"><img src="../../../../assets/img/waimai.png" alt=""></nuxt-link>
              </dd>
              <dd>
                <nuxt-link to="#"><img src="../../../../assets/img/zhenguo.png" alt=""></nuxt-link>
              </dd>
              <dd>
                <nuxt-link to="#"><img src="../../../../assets/img/dianping.png" alt=""></nuxt-link>
              </dd>
              <dd>
                <nuxt-link to="#"><img src="../../../../assets/img/maoyan.png" alt=""></nuxt-link>
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

  export default {
    name: 'navigation',
    components: {
      'm-card': card
    },
    mounted() {
      const navItem = this.$refs.navList.querySelectorAll('.navItem')
      navItem.forEach(item => {
        item.addEventListener('mouseenter', () => {
          item.classList.add('active')
          item.nextElementSibling && item.nextElementSibling.classList.remove('hidden')
        })
        item.addEventListener('mouseleave', () => {
          item.classList.remove('active')
        })
        this.$refs.navList.addEventListener('mouseleave', () => {
          item.nextElementSibling && item.nextElementSibling.classList.add('hidden')
        })
      })

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