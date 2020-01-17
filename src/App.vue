<template>
  <div id="app" >
      <color />  
      <mouse />  
  </div>
</template>

<script>

import Color from "@/components/Color";
import Mouse from "@/components/Mouse";

export default {
  name: 'app',
  components: {
    'color': Color,
    'mouse': Mouse
  },
  
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
