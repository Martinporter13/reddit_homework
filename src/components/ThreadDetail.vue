<template lang="html">
  <div>
    <h3>Title: {{thread.data.title}}</h3>
    <p>Subreddit: {{thread.data.subreddit}}</p>
    <p>Author: {{thread.data.author}}</p>
    <p>URL: {{thread.data.url}}</p>
  </div>
</template>

<script>
export default {
  name: 'thread-detail',
  props: ['thread']
}
</script>

<style lang="css" scoped>
</style>
