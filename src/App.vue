<template>
  <h1>{{ title }}</h1>
  <br/>
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <h1>Samundra Dhakal</h1>
      <p>Grab a coffee and start coding</p>
    </Modal>
  </div>
  <button @click.shift="toggleModal">open Modal</button>
  <input type="text" ref="name">
  <button @click="handleClick">Click me</button>
</template>

<script>
  import Modal from "./components/Modal-component"
export default {
  name: 'App',
  components: {
    Modal
},
  data(){
    return{
      title: "My first Vue App :) ",
      header:"Signup",
      text:"SignIn",
      showModal: false
    }
  },
  methods: {
    handleClick() {
      // console.log(this.$refs.name)
      this.$refs.name.classList.add("active")
      this.$refs.name.focus()
    },
    toggleModal(){
      this.showModal = !this.showModal
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
h1{
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
