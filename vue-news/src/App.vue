<template>
  <ToolBar></ToolBar>
  <router-view></router-view>
</template>

<script>
import ToolBar from './components/ToolBar.vue'

export default {
  name: 'App',
  components: {
    ToolBar
  },
  methods: {
    fetchData() {
      console.log('hello');
    }
  },
}
</script>

<style>
body {
  padding: 0;
  margin: 0;
}
</style>
