<template>
  <h1>{{ title }}</h1>
  <teleport to=".modals" v-if="modalShow">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:link>
        <a href="#">about</a>
        <a href="#">contact</a>
      </template>
      <h2>Modal header from behnam props</h2>
      <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Nostrum quod odit praesentium? Consequuntur quos numquam hic similique? Eum ab adipisci cum reprehenderit. Delectus iusto deserunt totam ipsum natus, animi sequi!</p>
    </Modal>
  </teleport>
    <teleport to=".modals" v-if="modalShowTwo">
      <Modal theme="sale" @close="toggleModalTwo">
      <template v-slot:link>
        <a href="#">about</a>
      </template>
      </Modal>
    </teleport>
  <button @click="toggleModal">Hide Modal</button>
  <button @click="toggleModalTwo">Hide Modal</button>
</template>

<script>
import Modal from './components/Modal'
export default {
  name: 'App',
  components:{
    Modal
  },
  data(){
    return{
      title: 'My First Vue App :)',
      modalShow: false,
      modalShowTwo: false
    }
  },
  methods:{
    toggleModal(){
      this.modalShow = !this.modalShow
    },
    toggleModalTwo(){
      this.modalShowTwo = !this.modalShowTwo
    }
  }
}
</script>

<style>
#app ,.modals{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
