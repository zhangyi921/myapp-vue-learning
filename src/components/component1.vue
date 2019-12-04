<template>
  <div class="hello">
    <h1>This is component1!!!!!!!!</h1>
    <h1>{{ computedMessage }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,<br>
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.
    </p>
    <button v-on:click="$emit('change-component', 'HelloWorld')">Go Back to HelloWorld component</button>
  </div>
</template>

<script>
export default {
  name: 'c1',
  props: {
    msg: String
  },
  computed:{
    computedMessage: function(){
      return this.msg + "=======computed value!"
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
