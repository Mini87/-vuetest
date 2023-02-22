<script>
export default{
data(){
  return {
    message: "Hello World!"
  }
},
methods:{
  reverseMessage(){
    this.message = this.message.split('').reverse().join('');
  },
  notify(){

  }
}
}
</script>
<template>
<h1>{{ message }}</h1>
<button @click="reverseMessage">Reverse Message</button>
<button @click="message+='!'">Append "!"</button>
<a href="https://vuejs.org" > 
A link with preventDefault()
</a>
</template>
<style>
button, a {
  display: block;
  margin-bottom: 1em;
}
</style>