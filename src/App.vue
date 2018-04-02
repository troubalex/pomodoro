<template>
  <div id="app">
    <Timer/>
  </div>
</template>

<script>
import Timer from './components/Timer.vue'
// eslint-disable-next-line
import scss from './assets/scss/base.scss'

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
  height: 100vh;
  justify-content: center;
}
h1 {
  font-size: 1.2rem;
  font-weight: 400;
}
</style>
