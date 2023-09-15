<script>
import SignUp from './components/SignUp.vue';
import HomePage from './components/HomePage.vue';
import Login from './components/Login.vue';
import Header from './components/Header.vue';
export default {
  name: 'App',
  // components: {
  //   SignUp,
  //   HomePage,
  //   Login
  // }
}
</script>

<template>
  <router-view />
</template>

<style>
#app {
  text-align: center;
}

body {
  padding: 0;
  margin: 0;
}
</style>
