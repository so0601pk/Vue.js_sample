<template>
  <div class="hello">
    <h1>{{ title }}</h1>
    <p>{{ message }}</p>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    title: String,
    messege: String,
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
  color: #f0f0f0;
  margin: 0px;
}
p{
  margin: 0px;
  color: #f0f0f0;
  font-size: 16pt;
}
</style>
