<template>
  <h1>Samundra Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">Play</button>
  <Block_item v-if="isPlaying" :delay="delay"/>
</template>

<script>
import Block_item from "./components/Block_item.vue"
export default {
  name: 'App',
  components: {Block_item},
  data(){
    return {
      isPlaying: false,
      delay:null
    }
  },
  methods: {
    start(){
      this.delay=2000 + Math.random()*5000
      this.isPlaying=true
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
</style>
