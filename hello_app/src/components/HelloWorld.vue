<template>
  <div class="hello">
    <h1>{{ title }}</h1>
    <p>{{ message }}</p>
    <hr>
    <p>val: {{ val }}</p>
    <div>* 2: <input type="number" v-model="a"></div>
    <div>^ 2: <input type="number" v-model="b"></div>
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
      message: 'バリデーションチェック',
      val:0,
    };
  },
  computed:{
    a:{
      get:function(){
        return this.val * 2;
      },
      set:function(value){
        this.val = Math.floor(value / 2);
      },
    },
    b:{
      get:function(){
        return this.val * this.val;
      },
      set:function(value){
        this.val = Math.floor(Math.sqrt(value));
      },
    },
  },
  created:function(){
    this.val = 10;
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
</style>
