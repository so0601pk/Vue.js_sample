<template>
  <div id="app">
    <HelloWorld v-bind:title="message" v-bind:num="num" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    HelloWorld
  },
  data: function(){
    return {
      message: 'validation',
      num:12
    };
  },
  methods:{
    appAction:function(message){
      this.result = '(*** you send :"' + message +'". ***)';
    }
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
