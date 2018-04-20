<template>
  <div id="app">
    <left-menu></left-menu>
    <div class="main">
      <router-view/>
    </div>
  </div>
</template>

<script>
  import LeftMenu from './components/LeftMenu.vue';
  
  export default {
    name: 'App',
    components: {
      LeftMenu
    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    height: 100%;
    width: 100%;
    margin: 0;
    padding: 0;
  }
  
  .main {
    width: 93%;
    float: left;
    padding: 0;
    height: 100%;
    background-color: white;
    margin-left: 1%;
  }
</style>
