<template>
  <h1>{{ title }}</h1>
  <p>Eligendi doloribus nam sint facere voluptas dolorem nihil aut et neque aut est vero.</p>
  <teleport to=".modals" v-if="showModal">
    <Modal @close="toggleModal">
      <h1>Modal 1</h1>
      <p>Aspernatur maiores at architecto sequi cum. Voluptas blanditiis incidunt explicabo.</p>
    </Modal>
  </teleport>
  <teleport to=".modals" v-if="showModal2">
    <Modal @close="toggleModal2">
      <h2>Modal 2</h2>
      <p>Cumque est odit eveniet animi quis eveniet placeat necessitatibus quo. Consequatur inventore praesentium aut eveniet sint magnam.</p>
    </Modal>
  </teleport>
  <button @click="toggleModal">modal 1</button>
  <button @click="toggleModal2">modal 2</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'Modal',
      showModal: false,
      showModal2: false
    }
  },
  methods: {
    handleClick() {
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    },
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModal2() {
      this.showModal2 = !this.showModal2
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

</style>
