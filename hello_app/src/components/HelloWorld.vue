<template>
  <div class="hello">
    <h1>{{ title }}</h1>
    <pre>{{ message }}</pre>
    <hr>
    <ul>
      <li><slot name="a" /></li>
      <li><slot name="b" /></li>
      <li><slot name="c" /></li>
    </ul>
    <hr>
    <slot />
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
      message: 'This is a message',
    };
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

.inner{
  color: red;
  font-size: 14pt;
}
.etc{
  color: green;
  background-color: #eee;
  font-size: 12pt;
  padding: 5px;
}
</style>
