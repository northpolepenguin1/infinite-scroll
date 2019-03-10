<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to My Animation App"/>
    <infinite-scroll2 />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
// import InfiniteScroll from './components/InfiniteScroll.vue'
import InfiniteScroll2 from './components/InfiniteScroll2.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    // InfiniteScroll,
    InfiniteScroll2
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
