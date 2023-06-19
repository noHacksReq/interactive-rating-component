

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

:root {
  --White: hsl(0, 0%, 100%);
  --LightGrey: hsl(217, 12%, 63%);
  --MediumGrey: hsl(216, 12%, 54%);
  --DarkBlue: hsl(213, 19%, 18%);
  --VeryDarkBlue: hsl(216, 12%, 8%);
  --Orange: hsl(25, 97%, 53%);
}

#app {
  height: 100%;
  width: 99%;
  font-family: Overpass, Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color:  black;
  display: flex;
  align-items: center;
  justify-content: center;
  
}
</style>
