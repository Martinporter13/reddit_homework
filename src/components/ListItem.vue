<template lang="html">
  <li v-on:click="handleClick">{{thread.data.title}}</li>
</template>

<script>
import{eventBus} from '../main.js'

export default {
  name: 'list-item',
  props: ['thread'],
  methods: {
    handleClick(){
      eventBus.$emit('thread-selected', this.thread);

    }
  }
}
</script>

<style lang="css" scoped>
</style>
