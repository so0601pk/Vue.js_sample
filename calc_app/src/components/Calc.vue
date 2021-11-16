<template>
  <div class="hello">
    <h1>{{ title }}</h1>
    <p>{{ message }}</p>
    <hr>
    <div>
      <div>
        <textarea v-model="fomula" cols="40" rows="5"></textarea>
      </div>
      <div>
        <button v-on:click="doAction">CALC</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Calc',
  props: {
    title: String
  },
  data:function(){
    return{
      message: 'Enter expression:',
      fomula:'0',
    };
  },
  methods:{
    doAction: function(){
      var arr = this.fomula.trim().split('¥n');//両端の空白を削除し、改行で分割
      var last = arr.pop();
      var fn = '';
      for(var n in arr ){
        if(arr[n].trum() != ''){
          fn += 'var' + arr[n] + ';';
        }
      }
      fn += 'return' + last + ';';
      var exp = 'function f(){ '+ fn +' } f();';
      var ans = eval(exp);
      this.message = 'answer:' + ans;
      var re = arr.join(';').trim();
      if(re != ''){
        re += ';'
      }
      re += last;
      this.$emit('result-event', re, ans);
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
