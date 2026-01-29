<template>
<div style="text-align:center;margin-top:50px;">
<h1>Click the Button Game!</h1>
<p>score: {{score}}</p>
<CounterButton :buttonClass="buttonClass" @clicked="increaseScore">
Click Me!
</CounterButton>
</div>
</template> 

<script>
import CounterButton from './components/CounterButton.vue'

export default {
  name: 'App',
  components: { CounterButton },
  data() {
    return {
score: 0,
buttonclass: 'default-button'
    }
  },
  methods: {
    increaseScore() {
      this.score += 1
      // change color after every click
      this.buttonClass = this.score % 2 === 0 ? 'default-button' : 'clicked-button'

    }
  }
}
</script>

<style>
body{
  font-family:arial, sans-serif;
}
</style>