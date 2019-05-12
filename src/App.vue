<template>
  <div id="app">
    <Menu />
  </div>
</template>

<script>
import Menu from './components/menu'

export default {
  name: 'app',
  components: {
    Menu
  }
}
</script>

<style>
body {
    margin: 0;
    padding: 0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
