<template>
  <div>
    <pre>
      {{ JSON.stringify(formValues,null,2) }}
    </pre> 
 
  <form @submit="submitForm">
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

    <div>
      <input type="checkbox" id="remoteWork" v-model="formValues.remoteWork"/>
      <label for="remoteWork"><b>Open to remote work?</b></label>
    </div>

    <div>
      <label for="yearsOfExperience">Years Of Experience</label>
     
      <label for="0-2">0-2</label>
      <input type="radio" id="0-2" value="0-2" v-model="formValues.yearsOfExpiriece"
       />
      
      <label for="3-5">3-5</label>
      <input type="radio" id="3-5" value="3-5" v-model="formValues.yearsOfExpiriece" />
     
      <label for="6-10">6-10</label>
      <input type="radio" id="6-10" value="6-10" v-model="formValues.yearsOfExpiriece" />
     
      <label for="10+">10+</label>
      <input type="radio" id="10+" value="10+" v-model="formValues.yearsOfExpiriece" />
    </div>

    <div>
      <label>Skill set</label>
      <input type="checkbox" id="html" value="html" v-model="formValues.skillSet"/>
      <label for="html">HTML</label>
      <input type="checkbox" id="c#" value="c#" v-model="formValues.skillSet"/>
      <label for="c$">C#</label>     
      <input type="checkbox" id="css" value="css"  v-model="formValues.skillSet"/>
      <label for="css">CSS</label>
    </div>    

    <div>
      <button>Submit</button>
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
      jobLocation:[],
      remoteWork:false,
      skillSet:[],
      yearsOfExpiriece:''
    },
   
   }
},
methods:{
 submitForm(event){
  event.preventDefault();
  console.log('Form values:', this.formValues)
 }
},
}
</script>


<style scoped>
h3 {
  margin: 40px;
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
