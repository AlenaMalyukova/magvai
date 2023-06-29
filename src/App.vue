<template>
  <Header/>
  <Main/>
</template>

<script>
import Header from './components/layout/Header.vue';
import Main from './pages/Main.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main,
  }
}
</script>

<style lang="scss">
@import '@/styles/mixins.scss';

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  
  button:hover {
    transition-duration: .3s;
  }


}

body{
  margin: 0 auto;
  background: #131313;
  color: #fff;
}
</style>
