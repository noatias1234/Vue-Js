<template>
  <div>
    <pre>
      {{ JSON.stringify(formValues,null,2) }}
    </pre> 
 
  <form>
    <div>
      <label for="name">Name</label>
      <input type="text" id="name" v-model="formValues.name">
    </div>
 
    <div>
      <label>Profile Summary</label>
      <textarea id="profile" v-model="formValues.profileSummary" />
     </div>

    <div>
      <label for="country">Country</label>
      <select id="country" v-model="formValues.country">
        <option value="">Select a country</option>
        <option value="Vietnam">Vietnam</option>
        <option value="India">India</option>
        <option value="Israel">Israel</option>
        <option value="USA">USA</option>
      </select>
    </div>    

    <div>
      <label for="jobLocation">Job Location</label>
      <select id="jobLocation"  multiple v-model="formValues.jobLocation">
        <option value="Vietnam">Vietnam</option>
        <option value="India">India</option>
        <option value="Israel">Israel</option>
        <option value="USA">USA</option>
      </select>
    </div>    
</form>
 
 </div>
</template>

<script>

export default {
  name: 'HelloWorld',
  data(){
	return{
    formValues:{
      name:'',
      profileSummary: '',
      country:'',
      jobLocation:[]
    },
   
   }
},
methods:{
 
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
