<template>
  <h1>{{ title }}</h1>
  <br/>
  <teleport to=".modals" v-if="showModal">
    <Modal theme="" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign up now</a>
        <a href="#">More Info</a>
      </template>
      <h1>Samundra Dhakal</h1>
      <p>Grab a coffee and start coding</p>
    </Modal>
  </teleport>

  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <h1>Wow</h1>
      <p>Coffee is not so hot. Replace and get the hot one.</p>
    </Modal>
  </div>
  <button @click.shift="toggleModal">open Modal(Press Shift)</button>
  <button @click="toggleModalTwo">open Modal</button>
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
      showModal: false,
      showModalTwo: false
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
    },
    toggleModalTwo(){
      this.showModalTwo = !this.showModalTwo
    }
  }

}
</script>

<style>
#app, .modals {
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
