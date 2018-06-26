<template>
  <div id="app">
    <router-view/>
    <rodo_banner></rodo_banner>
  </div>
</template>

<script>
import rodo_banner from './components/rodo_banner.vue';

export default {
  name: 'App',
  components:{
    rodo_banner,
  }
}
</script>

<style>
*{
  box-sizing: border-box;
}
body{
  background: #eeebe8;
  margin:0;
}
#app {
  font-family: 'Teko', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #6b6e70;
  font-size: 16px;
}
</style>
