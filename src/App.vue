<template>
  <div id="app">
    <Menu @animationChange="animationChange" />
    <div class="main">
        <component :is="cname"></component>
    </div>
  </div>
</template>

<script>
import Menu from './components/menu'
import FadeSlide from './components/fadeSlide'
import FadeIn from './components/fadeIn'
export default {
  name: 'app',
  data () {
      return {
          cname: ''
      }
  },
  components: {
    Menu,
    FadeSlide,
    FadeIn
  },
  methods: {
      animationChange (cname) {
        this.cname = cname
      }
  }
}
</script>

<style lang="less">
body {
    margin: 0;
    padding: 0;
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        color: #2c3e50;
        .main {
            position: absolute;
            left: 130px;
            top: 0;
            width: calc(100% - 130px);
            height: 100%;
            overflow: auto;
        }
    }
}
</style>
