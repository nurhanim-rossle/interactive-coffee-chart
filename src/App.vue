<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <CoffeeChart msg="How caffeinated is your coffee?"/>
  </div>
</template>

<script>
import CoffeeChart from './components/CoffeeChartNew.vue'

export default {
  name: 'app',
  components: {
    CoffeeChart
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Caveat|Montserrat|Nanum+Gothic+Coding|PT+Mono|Poiret+One&display=swap');

#app {
  /*font-family: 'Avenir', Helvetica, Arial, sans-serif;*/
  /*font-family: 'Poiret One', cursive;*/
  
  /*font-family: 'Nanum Gothic Coding', monospace;*/
  /*font-family: 'Montserrat', sans-serif;*/
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100vh;
  padding: 0;
  margin: 0;

  font-family: 'PT Mono', monospace, Helvetica, Arial, sans-serif;

  background-color: #3C3C3C;
  color: #ffffff;
  /*background-image: url('./assets/images/bg.jpg');*/
  /* Full height */

  /* Center and scale the image nicely */
  /*background-position: center;
  background-repeat: no-repeat;
  background-size: cover;*/
}
</style>
