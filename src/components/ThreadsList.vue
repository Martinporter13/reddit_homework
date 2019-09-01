<template lang="html">
  <div>
    <ul>
      <list-item v-for="(thread, index) in threads" :thread="thread" :key="index"></list-item>
    </ul>
  </div>

</template>

<script>
import ListItem from './ListItem.vue';

export default {
  name: 'threads-list',
  props: ['threads'],
  components: {
    "list-item": ListItem
  }
}
</script>

<style lang="css" scoped>
</style>
