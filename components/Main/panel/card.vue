<template>
  <nuxt-link tag="div" to="#" class="panel-card">
    <div class="content">
      <img :src="detail.img.src" :alt="detail.img.alt"
           :style="{width: detail.img.width, height: detail.img.height}">
      <h3>{{detail.title}}</h3>
      <p>{{detail.description}}</p>
    </div>
    <div class="price">
      <p>￥<span>{{detail.price}}</span></p>
      <slot></slot>
    </div>
  </nuxt-link>
</template>

<script>
  export default {
    name: 'panel-card',
    props: {
      detail: {  // 包含 title Img(对象, 包括宽高和src) description price
        type: Object,
        default() {
          return {
            img: {},
            title: '',
            description: '',
            price: ''
          }
        }
      }
    }
  }
</script>

<style scoped lang="scss">




  .panel-card {
    padding: 10px 10px 6px;
    background-color: #fff;
    transition: background-color 500ms;
    cursor: pointer;

    &:hover {
      background: #F4F4F4;
      border-radius: 4px;
    }

    .content {
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      img {
        border-radius: 4px;
        margin-bottom: 11px;
      }
      h3 {
        font-size: 16px;
        white-space: nowrap;
        font-weight: 500;
        color: #222;
        margin-bottom: 8px;
        height: 22px;
        line-height: 22px;
      }
      p{
        font-size: 12px;
        color: #999;
        line-height: 18px;
        height: 18px;
        margin-bottom: 7px;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
      }
    }
    .price{
      display: flex;
      p {
        color: #FF6600;
        font-size: 14px;
        span{
          font-size: 22px;
        }
      }
    }
  }
</style>