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
#app{
  background-color:rgb(243, 241, 234);
  padding-left:10vh;
   padding-right:10vh;
}
</style>
