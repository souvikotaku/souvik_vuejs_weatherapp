<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <Gotbox msg="Souvik Game of Thrones App"/>
</template>

<script>
import Gotbox from './components/Gotbox.vue'

export default {
  name: 'App',
  components: {
    Gotbox
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
