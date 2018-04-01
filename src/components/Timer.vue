<template>
  <div class="container">
    <h1>🍅 Pomodoro Timer 🍅</h1>
    <div class="timer">{{ timer }}</div>
    <button v-on:click="startCounter">{{ buttonLabel }}</button>
  </div>
</template>

<script>

export default {
  name: 'Timer',
  data () {
    return {
      buttonLabel: 'Start',
      intervalId: 0,
      timer: 1500
    }
  },
  methods: {
    updateTimer () {
      this.timer = this.timer - 1
    },
    startCounter () {
      if (this.intervalId === 0) {
        this.intervalId = setInterval(this.updateTimer, 1000)
        this.buttonLabel = 'Pause'
      } else {
        clearInterval(this.intervalId)
        this.intervalId = 0
        this.buttonLabel = 'Start'
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1 {
    font-size: 1.2rem;
    font-weight: 400;
  }
  button {
    background-color: white;
    border-radius: 2px;
    border: 1px solid tomato;
    color: tomato;
    cursor: pointer;
    font-size: 1em;
    padding: 0.5em 1em;
    transition: all 300ms ease-in-out;
  }
  button:hover {
    background-color: tomato;
    box-shadow: 2px 2px 4px rgba(0,0,0,0.12);
    color: white;
  }
  .container {
    align-items: center;
    display: flex;
    flex-direction: column;
  }
  .timer {
    color: tomato;
    font-family: 'Bungee', cursive;
    font-size: 6rem;
    font-weight: 700;
    letter-spacing: 0.05em;
    margin: 2rem 0;
  }
</style>
