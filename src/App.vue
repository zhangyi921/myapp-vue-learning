<template>
  <div id="app">
    <button @click="animate()">
      Toggle render
    </button>
    <div  class="logo">
      <transition
        name="bounce"
      >
        <!-- <p v-if="show">hello</p> -->
        <img v-if="show" alt="Vue logo" src="./assets/logo.png">
      </transition>
    </div>
    <transition name="component-fade" mode="out-in">
      <component v-bind:is="componentToShow" v-on:change-component="componentToShow = $event"></component>
    </transition>
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
      show: true
    }
  },
  methods: {
    animate: function() {
      var self = this;
      self.show = !self.show;
      setTimeout(function(){ self.show = !self.show; }, 500);
    }
  }
}
</script>

<style>
.logo{
  height: 20em;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.component-fade-enter-active, .component-fade-leave-active {
  transition: opacity .3s ease;
}
.component-fade-enter, .component-fade-leave-to
/* .component-fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
.bounce-enter-active {
  animation: bounce-in .5s;
}
.bounce-leave-active {
  animation: bounce-in .5s reverse;
}
@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
}
</style>
