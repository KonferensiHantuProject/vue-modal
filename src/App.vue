<template>
  <h1>{{ title }}</h1>
  <p>Selamat Datang</p>
  <teleport to=".modals" v-if="showModal">
    <Modal :theme="theme" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Daftar Sekarang</a>
        <a href="#">Informasi Tambahan</a>
      </template>
      <h1>Pass Slot</h1>
      <p>Ini adalah text</p>
    </Modal>
  </teleport>

  <!-- Second Modal -->
  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <h1>Daftar</h1>
      <p>Ini adalah text kedua</p>
    </Modal>
  </div>

  <button @click="toggleModalTwo">Buka Modal</button>
  <button @click.alt="toggleModal">Buka Modal (alt)</button>
</template>

<script>
// import the modal from component
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components:{
    Modal
  },
  data () {
    return {
      title: 'Aplikasi Vue Pertama',
      header: "Ini adalah Header",
      theme: "sale",
      text: "Ini adalah text",
      showModal: false,
      showModalTwo: false
    }
  },
  methods:{
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
