<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <Rating :rate="0" :maxStars="5" :hasCounter="true"/>
  </div>
</template>

<script>
import Rating from './components/Rating.vue'

export default {
  name: 'App',
  components: {
    Rating
  }
}
</script>

<style>
#app {
  font-family: 'Spartan', sans-serif;   
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}
</style>
