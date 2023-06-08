

<script>
import MainComp from './components/MainComp.vue'

export default {
  name: 'App',
  components: {
    MainComp
  }
}
</script>
<template>
  
  <MainComp />
</template>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color:  hsl(216, 12%, 54%);
  display: flex;
  align-items: center;
  justify-content: center;
  
}
</style>
