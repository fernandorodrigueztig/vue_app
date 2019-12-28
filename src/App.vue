<template>
  <div id="app">
   <listaComponent></listaComponent>

  </div>
</template>

<script>
import listaComponent from './components/lista'

export default {
  name: 'app',
  components: {
    listaComponent
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
