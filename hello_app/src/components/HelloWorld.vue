<template>
  <div class="hello">
    <h1>{{ title }}</h1>
    <pre>{{ message }}</pre>
    <hr>
    <div>
      <input type="text"
      v-on:keydown.delete="clear"
      v-on:keypress="type"
      v-on:keydown.space="space"
      v-on:keydown.enter="enter"
      >
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
      if(event.key == 'Enter'){
        return;
      }
      this.message += event.key + ' ';
      event.target.value = '';
    },
    clear: function(){
      this.message = '';
    },
    space: function(){
      this.message += '_ ';
    },
    enter: function(event){
      var res =this.message.split(' ').join('')
      this.message = res.split('_').join(' ');
      event.target.value = '';
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

/* pre{
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
} */
</style>
