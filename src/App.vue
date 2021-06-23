<template>
  <div id="app">
    <TodoHome msg="Welcome!" />
  </div>
</template>

<script>
import TodoHome from './components/TodoHome.vue'
export default {
  name: 'App',
  components: {
    TodoHome,
  },
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  width: 100vw;
  min-height: 100vh;
  background-color: rgba(203, 210, 240);
}
</style>
