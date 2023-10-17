<template>
  <div id="app">
    <ul>
      <li v-for="item in users" :key="item.id">
            {{ item.id }}      : {{ item.name  }}
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'App',
  data(){
    return {
      users:[]
    }
  },
  mounted(){
    axios.get('/api/users').then((response)=>{
      this.users = response.data;
    })
  },
}
</script>

<style>
</style>
