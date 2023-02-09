<template>
  <div>
<div v-bind:id="headingId">HEY</div>
<h2 v-if="num === 0"> The number is zero</h2>
 <h2 v-else-if="num > 0"> The number is poistive</h2>
<h2 v-else-if="num < 0"> The number is negative</h2>
<h2 v-else>Not a number</h2> 

<!-- array of strings -->
<h3 v-for="name in names" :key="name">{{ name }}</h3>
<h3 v-for="(name,index) in names" :key="name">{{ index }} {{ name }}</h3>

<!-- array of object -->
<h3 v-for="name in fullNames" :key="name.first">{{ name.first }} {{ name.last }}</h3>

<!-- array of arrays -->
<div v-for="actor in actors" :key="actor.name">
  <h2>{{ actor.name }}</h2>
  <h3 v-for= "movie in actor.movies" :key="movie"> {{movie}}</h3>
</div>
</div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
	return{
		name: '<b>someString</b>',
		headingId: '123',
		isDisabled: true,
    num: 3,
    names: ['Roi','Simon','Bar', 'Vadim','David'],
    fullNames: [
      {first:'Roi', last:'Peretz'},
      {first:'Simon', last:'Kriheli'},
      {first:'Bar', last:'Noa'},
      {first:'Vadim', last:'A'},
      {first:'David', last:'M'},
    ],
    actors:[
      {
        name:'Christian Bale',
        movies:['Batman','The prestige'],
      },
      {
        name:'Leonardo Decaprio',
        movies:['Titanic','Unknown'],
      },
    ]
	};
}
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
