<template>
  <div class="m-panel">
    <slot></slot>
  </div>
</template>

<script>
  import Vue from 'vue'
  export default {
    name: 'panel',
    props: {
      selected: {
        type: String | Number,
        default: 0
      }
    },
    data(){
      return {
        eventBus: new Vue()
      }
    },
    provide(){
      return {
        eventBus: this.eventBus
      }
    },
    mounted() {
      this.eventBus.$emit('assignSelected', this.selected)
      this.eventBus.$on('changeSelected', (idx)=>{
        this.$emit('update:selected', idx)
        this.eventBus.$emit('assignSelected', idx)
      })
    }
  }
</script>

<style scoped>

</style>