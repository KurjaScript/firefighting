<template>
  <div id="app">
    <enterprise-info></enterprise-info>
  </div>
  
</template>

<script>
import EnterpriseInfo from './components/chemicals/EnterpriseInfo.vue';

export default {
  name: 'App',
  components: {
    EnterpriseInfo
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
