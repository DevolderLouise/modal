<template>
  <div class="overlay" @click.self="closeModal">
    <div class="modal">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    closeModal() {
      this.$emit('close')
    }
  }
}
</script>

<style>
  .modal {
    width: 40rem;
    padding: 2rem;
    margin: 10rem auto;
    background: white;
    border-radius: 1rem;
  }

  .overlay {
    top: 0;
    position: fixed;
    background: rgba(0, 0, 0, 0.5);
    width: 100%;
    height: 100%;
  }

  .modal h1 {
    border: none;
    padding: 0;
  }

  .modal p {
    font-style: normal;
  }
</style>