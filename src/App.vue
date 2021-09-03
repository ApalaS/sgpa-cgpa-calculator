<template>
  <div id="app">
    <sgpa/>
    <cgpa/>
  </div>
</template>

<script>
import cgpa from './components/cgpa.vue'
import sgpa from './components/sgpa.vue'

export default {
  name: 'App',
  components: {
    cgpa,
    sgpa,
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
  margin-top: 30px;
}
</style>
