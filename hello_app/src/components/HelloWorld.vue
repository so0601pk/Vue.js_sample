<template>
  <div class="hello">
    <h1>{{ title }}</h1>
    <p>{{ message }}</p>
    <hr>
    <p>Number: {{ num }}</p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    title: String,
    num: Number,
  },
  data:function(){//data=変数だが、関数の形式で記述しなければならない
    return{
      message: 'バリデーションチェック',
    };
  },
  methods:{
    doAction: function(){
      this.message = 'こんにちは、' + this.input + 'さん！';
      this.$emit('result-event', this.input);
    }
  }
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
