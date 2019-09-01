<template lang="html">
  <div class="">
    <h1> Scottish Football Reddit Threads</h1>
    <div>
      <threads-list :threads='threads'></threads-list>
      <thread-detail v-if="selectedThread" :thread="selectedThread"></thread-detail>
    </div>
  </div>
</template>

<script>
import ThreadsList from './components/ThreadsList.vue';
import ThreadDetail from './components/ThreadDetail.vue';
import{eventBus} from './main.js';

export default {
  name: 'app',
  data(){
    return {
      threads: [],
      selectedThread: null
    };
  },
  mounted(){
    fetch('https://www.reddit.com/r/ScottishFootball.json')
    .then(res => res.json())
    .then(data => this.threads = data.data.children)


  eventBus.$on('thread-selected', (thread) =>{
    this.selectedThread = thread;
    })
  },
  components: {
    "threads-list": ThreadsList ,
    "thread-detail": ThreadDetail
  }

}
</script>

<style lang="css" scoped>

</style>
