<template>
  <div id="app">
    <Timer/>
  </div>
</template>

<script>
import Timer from './components/Timer.vue'

export default {
  components: {
    Timer
  }
}
</script>

<style>
#app {
  align-items: center;
  color: #333;
  display: flex;
  flex-direction: column;
  font-family: 'Open Sans', sans-serif;
  height: 80vh;
  margin-top: 2em;
}
</style>
