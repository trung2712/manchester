<template>
  <div id="app">
    <TiVi ten="This is my TV"></TiVi>
  </div>
</template>

<script>
import TiVi from './components/TiVi.vue';

export default {
  name: 'App',
  components: {
    TiVi
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
