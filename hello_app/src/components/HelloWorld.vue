<template>
  <div class="hello">
    <h1>{{ title }}</h1>
    <pre v-on:click="clear">{{ message }}</pre>
    <hr>
    <div>
      <input type="text" v-on:keydown="type">
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    title: String,
  },
  data:function(){//data=変数だが、関数の形式で記述しなければならない
    return{
      message: '',
    };
  },
  methods:{
    type: function(event){
      this.message += event.key + '';
      if(event.key == "Escape"){
        this.message = '';
      }
      event.target.value = '';
    },
    clear: function(){
      this.message = '';
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
div {
  margin: 0px;
  padding:0px;
  text-align: left;
}
h1 {
  font-size: 72pt;
  font-weight: bold;
  text-align: right;
  letter-spacing: -8px;
  color: black;
  margin: 0px;
}
p{
  margin: 0px;
  color:black;
  font-size: 16pt;
}

pre{
  font-size: 14pt;
}
div.out{
  padding: 5px 0px;
  background-color: #eee;
  width: 300px;
  height: 200px;
}
div.mid{
  padding: 5px;
  background-color: #ddd;
  width: 200px;
  height: 175px;
}
div.in{
  padding: 5px 0px;
  background-color: #ccc;
  width: 100px;
  height: 150px;
}
</style>
