<template>
  <h1>{{ title }}</h1>
  <p>Welcome</p>
  <teleport to=".modals" v-if="showModal">
    <Modal  theme="" @close="toggleModal">
      <template v-slot:links> 
        <a href="#">Sign Up Now</a>
        <a href="#">More Info</a>
      </template>
      <h1>Ninja Giveaway!</h1>
      <p>Grab your ninja swag for half price!</p>
    </Modal>
  </teleport>

  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
     
      <h1>Sign Up to the Newsletter</h1>
      <p>For Updates and Promo Codes!</p>
    </Modal>
  </div>
  <button @click="toggleModal">Open Modal </button>
  <button @click="toggleModalTwo">Open Modal 2</button>
  
  </template>
  
  <script>
    //challenge
    //  -create an extra button to open a different modal
    //  -usre the same modal component but pass in a different template (slot)
    //  -use a different method (e.g. toggleModaşTwo) and data (e.g. showModalTwo)
    
  import Modal from './components/Modal'
  
  export default {
    name: 'App',
    components: { Modal },
    data() {
      return {
        title: 'My First Vue App',
        showModal: false,
        showModalTwo: false,
      }
    },
    methods: {
      toggleModal(){
        this.showModal = !this.showModal
      },

      toggleModalTwo(){
        this.showModalTwo = !this.showModalTwo
      },
    }
  
  }
  </script>
  
  <style >
  #app, .modals {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
  h1{
    border-bottom: 2px solid #ddd;
    display: inline-block;
    padding-bottom: 10px;
  }
  </style>