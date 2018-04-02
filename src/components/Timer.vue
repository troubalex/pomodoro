<template>
  <div class="container">
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
<style scoped lang="scss">
  .container {
    align-items: center;
    background-color: white;
    border: 1px solid tomato;
    border-radius: 3px;
    box-shadow: 2px 2px 4px rgba(0,0,0,0.12);
    display: flex;
    flex-direction: column;
    padding: 1.5rem 2.5rem 2rem;
  }
  .timer {
    color: tomato;
    font-family: 'Bungee', cursive;
    font-size: 12vw;
    font-weight: 700;
    letter-spacing: 0.05em;
    margin: 2rem 0;
  }
</style>
