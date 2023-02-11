<template><div>
<h2>{{ name }}</h2>
 <!-- <button v-on:click="name = 'Batman'">Change Name</button> -->
 <button v-on:click="changeName($event), increaseMethod(1,$event)">Change Name</button>


  <h2>{{ count }}</h2>
 
  <button v-on:click="count += 1">Increase</button>
  <button v-on:click="count -= 1">Decrease</button>

  <button @click="increaseMethod(1, $event)">Increase</button>
  <button @click="decreaseMethod(1)">Decrease</button></div>
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
  changeName(event){
    this.name='Batman'
    console.log("event",event);
  },
  increaseMethod(num, event){
    this.count+=num;
    console.log('Event',event)
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
