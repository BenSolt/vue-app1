<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <MyHelloWorld  msg="My Vue Todo Component"/>
  <DogApi />
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
//import MyHelloWorld from './components/MyHelloWorld.vue'
import DogApi from './components/DogApi.vue'

export default {
  name: 'App',
  components: {
    //HelloWorld,
    // MyHelloWorld,
    DogApi
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
  margin-top: 20px;
}
</style>
