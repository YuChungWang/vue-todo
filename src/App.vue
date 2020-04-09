<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" class="logo">
    <VueToDo msg='VUE TO DO LIST'/>
  </div>
</template>

<script>
import VueToDo from './components/VueToDo'

export default {
  name: 'App',
  components: {
    VueToDo
  }
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.logo {
  width: 60px;
  height: 60px;
}
</style>
