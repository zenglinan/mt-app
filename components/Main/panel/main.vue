<template>
  <main class="panel-main" v-show="selected === id">
    <slot></slot>
  </main>
</template>

<script>
  export default {
    name: 'panel-main',
    inject: ['eventBus'],
    props: {
      id: {
        type: String | Number
      }
    },
    data(){
      return {
        selected: undefined
      }
    },
    mounted(){
      this.eventBus.$on('assignSelected', (idx)=>{
        this.selected = idx
      })
    },
  }
</script>

<style scoped lang="scss">
  .panel-main {
    position: relative;
    padding: 6px 10px 10px;
    display: flex;
    flex-wrap: wrap;
    border: 1px solid #e5e5e5;
    border-top: none;
  }
</style>