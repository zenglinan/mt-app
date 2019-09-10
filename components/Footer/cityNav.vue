<template>
  <section class="cityNav">
    <h3>美团导航</h3>
    <div class="section" v-for="(item,idx) in cityNav" :key="idx">
      <h3>{{item.title}}</h3>
      <ul>
        <li v-for="(t,idx) in item.child" :key="idx">
          <nuxt-link to="#" class="hoverable">{{t}}</nuxt-link>
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
  export default {
    name: 'cityNav',
    data() {
      return {
        cityNav: [
          {
            title: '热门城市',
            child: [
              '长沙',
              '成都',
              '沈阳',
              '北京',
              '太原',
              '长春',
              '昆明',
              '合肥',
              '南京',
              '宁波',
              '深圳',
              '厦门',
              '福州',
              '东莞',
              '济南',
              '广州',
              '上海',
              '青岛',
              '无锡',
              '重庆']
          },
          {
            title: '热门分类',
            child: [
              '酒店',
              '美食',
              '休闲娱乐',
              '运动健身',
              '生活服务',
              '上门服务',
              '购物',
              '时尚购',
              '本地购物',
              '结婚',
              '摄影写真',
              '宴会',
              '丽人',
              '母婴亲子',
              '学习培训',
              '家装',
              '汽车服务',
              '医疗',
              '宠物'
            ]
          },
          {
            title: '周边热门',
            child: [
              '佛山酒店',
              '南沙美食',
              '顺德休闲娱乐',
              '佛山运动健身',
              '顺德生活服务',
              '佛山上门服务',
              '南沙购物',
              '顺德时尚购',
              '南沙本地购物',
              '顺德结婚',
              '南沙摄影写真',
              '佛山宴会',
              '佛山丽人',
              '佛山母婴亲子',
              '顺德学习培训',
              '南沙家装',
              '南沙汽车服务',
              '南沙医疗',
              '南沙宠物'
            ]
          }
        ]
      }
    }
  }
</script>

<style scoped lang="scss">
  .cityNav{
    margin: 40px 0;
    border: 1px solid #e5e5e5;
    border-radius: 4px;
    h3{
      font-size: 16px;
      font-weight: normal;
      padding: 20px;
    }
    .section {
      display: flex;
      align-items: flex-start;
      padding-top: 12px;
      h3 {
        white-space: nowrap;
        font-size: 14px;
        padding-top: 0;
        margin-top: -2px;
      }
      ul {
        display: flex;
        flex-wrap: wrap;
        flex-grow: 1;
        border-bottom: 1px solid #e5e5e5;
        li {
          width: 100px;
          height: 17px;
          font-size: 12px;
          margin-bottom: 13px;
          color: #666
        }
      }
    }
  }
</style>