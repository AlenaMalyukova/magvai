<template>
  <Header/>
  <Intro />
  <app-footer/>
</template>

<script>
import Header from './components/layout/Header.vue';
import Intro from './components/Intro.vue';

export default {
  name: 'App',
  components: {
    Header,
    Intro
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #fff;
  background: #131313;
}

body{
  margin: 0 auto;
}
</style>
