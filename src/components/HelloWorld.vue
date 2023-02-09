<template> <div>
  <template v-for="name in names" >
   <h2 :key="name" v-if="name === 'Simon'">{{ name }}</h2>
</template></div>

<!-- calculate -->
<h2>{{ 2+3+5 }}</h2>
<h2>Add Method - {{ add(2,3,5) }}</h2>
<h2>Multipl method - {{ multiply(5) }}</h2>
<h2>Multipl method - {{ multiply(baseValue) }}</h2>
</template>

<script>
export default {
  name: 'HelloWorld',
  data(){
	return{
    names: ['Roi','Simon','Bar', 'Vadim','David'],
    baseMultiply:5,
    baseValue:2,
   }
},
methods:{
  add(a,b,c)
  { 
    return a+b+c
  },
  multiply(num){
    return num * this.baseMultiply
  },
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
