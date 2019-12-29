<template>
  <div id="app">
   <listaComponent></listaComponent>
    <videoplayer></videoplayer>
  </div>
</template>

<script>
import listaComponent from './components/lista'
import videoplayer from './components/videoplayer'


export default {
  name: 'app',
  components: {
    listaComponent,
    videoplayer
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
