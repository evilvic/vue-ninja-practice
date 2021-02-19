<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <teleport to=".modals" v-if="showModal">
    <Modal 
      theme="sale"
      @close="toggleModal"
    >
      <h1>Ninja Givaway!</h1>
      <p>Grab your ninja swag for half price!</p>
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
    </Modal>
  </teleport>
  <teleport to=".modals" v-if="showModalTwo">
    <Modal 
      @close="toggleModalTwo"
    >
      <h1>Matrix</h1>
      <p>Pick a pill!</p>
      <template v-slot:links>
        <a href="#">blue</a>
        <a href="#">red</a>
      </template>
    </Modal>
  </teleport>
  <button @click="toggleModal">open modal</button>
  <button @click="toggleModalTwo">open modal 2</button>
</template>

<script>
import Modal from './components/Modal'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My First Vue App :)',
      header: 'Sign up for the Giveaway!',
      text: 'Grab your ninja swag for half price!',
      showModal: false,
      showModalTwo: false
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
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
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
