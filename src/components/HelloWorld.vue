<template><div>
<h2>{{ name }}</h2>
 <button v-on:click="name = 'Batman'">Change Name</button>
 
  <h2>{{ count }}</h2>
 
  <button v-on:click="count += 1">Increase</button>
  <button v-on:click="count -= 1">Decrease</button>

  <button v-on:click="increaseMethod(1)">Increase</button>
  <button v-on:click="decreaseMethod(1)">Decrease</button></div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data(){
	return{
    name:'Vue App',
    names: ['Roi','Simon','Bar', 'Vadim','David'],
    baseMultiply:5,
    baseValue:2,
    count:0
   }
},
methods:{
  increaseMethod(num){
    this.count+=num;
  },
  decreaseMethod(num){
    this.count-=num;
  }
},
}
</script>


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
