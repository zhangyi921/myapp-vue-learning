<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <component v-bind:is="componentToShow" v-on:change-component="componentToShow = $event"></component>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import component1 from './components/component1'

export default {
  name: 'app',
  components: {
    HelloWorld,component1
  },
  data: function(){
    return {
      componentToShow: "HelloWorld",
    }
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
