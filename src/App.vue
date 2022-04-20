<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
 <div v-if="modalShow">
    <Modal @close="toggleModal">
      <template v-slot:links>
        <a href="">Link 1</a>
        <a href="">Link 2</a>
      </template>
      <h1>Modal tittle</h1>
      <p>Lorem ipsum dolor sit amet.</p>
    </Modal>
 </div>
 <teleport to="#modals" v-if="modalShow2">
       <Modal @close="toggleModal2">
      <template v-slot:links>
        <a href="">Link 1</a>
        <a href="">Link 2</a>
      </template>
      <h1>Modal tittle 2</h1>
      <p>Lorem ipsum dolor sit amet.</p>
    </Modal>
 </teleport>
 <button @click="toggleModal">open modal</button>
 <button @click="toggleModal2">open modal 2</button>
</template>

<script>
import Modal from '@/components/Modal.vue';
export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      title: 'Vue Modals',
      modalShow: false,
      modalShow2: false
    }
  },
  methods: {
    toggleModal(){
      this.modalShow = !this.modalShow;
    },
    toggleModal2(){
      this.modalShow2 = !this.modalShow2;
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
