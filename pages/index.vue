<template>
  <div class="page-index" title="美团网">
    <m-main></m-main>
  </div>
</template>

<script>
  import main from '@/components/Main/index'

  export default {
    name: 'indexMain',
    head(){
      return {
        title: "美团网"
      }
    },
    components: {
      'm-main': main
    }
  }
</script>

<style>
</style>
