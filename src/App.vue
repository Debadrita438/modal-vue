<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <teleport to='.modals' v-if='showModal'>
    <Modal theme='sale' @close= "toggleModal">
      <h1>Sign in for the Giveaway!</h1>      
      <p>Grab your style in half price!</p>
      <template v-slot:links>
        <a href="#">Sign Up Now</a>
        <a href="#">More Info</a>
      </template>
    </Modal>
  </teleport>

  <teleport to='.modals' v-if='showModalTwo'>
    <Modal @close= "toggleModalTwo">
      <h1>Subscribe For The Newsletter</h1>      
      <p>To fulfill your curiosity!</p>
    </Modal>
  </teleport>

  <button @click.left='toggleModal'>Open Modal</button>
  <div>
    <button @click.left='toggleModalTwo'>Open Modal 2</button>
  </div>
</template>

<script>
  import Modal from './components/Modal'
  
  export default {
    name: 'App',
    components: { Modal },
    data() {
      return {
        title: 'My First Vue App :)',
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
      },
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

  h1 {
    border-bottom: 1px solid #ddd;
    display: inline-block;
    padding-bottom: 10px;
  }
</style>
