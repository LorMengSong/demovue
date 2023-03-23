<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <Home />
  <h1>Hello API CALL</h1>
  <p  v-for="item in list" :key="item.id">
      {{ item.email }}
  </p>
  <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Home from './components/Home.vue';
import axios from "axios";
export default {
  name: 'App',
  async mounted(){
      let result = await axios.get('https://reqres.in/api/users?page=1');
      console.warn(result.data.data);
      this.list = result.data.data;
  },
  components: {
    HelloWorld,
    Home,
    
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
