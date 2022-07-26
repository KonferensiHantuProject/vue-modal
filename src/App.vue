<template>
  <h1>{{ title }}</h1>
  <Modal :header="header" :text="text" :theme="theme" />
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
      text: "Ini adalah text"
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
