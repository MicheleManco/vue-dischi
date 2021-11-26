<template>
  <div id="app">
    <Myheader/>
    <Albums/>
    <Album/>
  </div>
</template>

<script>
import Myheader from './components/Myheader.vue'
import Albums from './components/Albums.vue'


export default {
  name: 'App',
  components: {
    Myheader,
    Albums
  }
}
</script>

<style lang="scss">
* {
  box-sizing: border-box;
  padding: 00;
  margin: 0;
}
#app {
  background-color: #1e2d3b;
}
</style>
