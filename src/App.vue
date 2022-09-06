<template>
  <h1>Samundra Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">Play</button>
  <Block_item v-if="isPlaying" :delay="delay" @end="endGame"/>
  <Results_item v-if="showResult" :score="score"/>
</template>

<script>
import Block_item from "./components/Block_item.vue"
import Results_item from "./components/Results_item.vue"
export default {
  name: 'App',
  components: {Block_item, Results_item},
  data(){
    return {
      isPlaying: false,
      delay:null,
      score: null,
      showResult: false
    }
  },
  methods: {
    start(){
      this.delay=2000 + Math.random()*5000
      this.isPlaying=true
      this.showResult = false
    },
    endGame(value) {
      this.score = value
      this.isPlaying = false
      this.showResult = true
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
button{
  background: #0faf87;
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 16px;
  letter-spacing: 1px;
  cursor: pointer;
  margin: 10px;
}
button[disabled]{
  opacity: 0.2;
  cursor: not-allowed;
}
</style>
