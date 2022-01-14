<template>
  <h1 style="text-align:center">Api Data</h1>
  <ul class="item" v-for="item in list" :key="item.id">
    <li>{{item.id}}</li>
     <li>{{item.first_name}}</li> 
     <li>{{item.email}}</li> 
  </ul>
</template>

<script>
import axios from 'axios';

export default {
    name: 'App',
    data(){
      return{
        list:[],
      }
    },
async mounted(){
  let result = await axios.get("https://reqres.in/api/users?page=1");
  this.list = result.data.data;
},
}
</script>

<style>

.item li{
  display: inline-block;
  width: 180px;
  border: 1px solid;
  text-align: center;
  padding: 5px;
}
</style>
