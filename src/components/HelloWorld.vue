<template>
  <div class="hello">
  
  <form @submit.prevent="addSkill" >
    <input type="text" placeholder="enter your skill ..." v-model="skill" >
  </form>

  <ul>
    <li  v-for="(data ,index) in skills" :key="index">{{data.skill}} <span v-on:click="deleteOn(index)">x</span> </li>
  </ul>
     
   
  </div>
</template>

<script>
export default {
  name: 'HelloWorld', 
 data(){
   return{
      skill:'',
     skills:[
       {"skill":"ganesh"},
       {"skill":'ganesh'},
       {"skill":'ganesh'}
     ]
   }
 },
 methods:{
   addSkill(){
     this.skills.push({skill:this.skill})
     this.skill=''
   },
   deleteOn(id){
   this.skills.splice(id,1);
    }
 },
 
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
