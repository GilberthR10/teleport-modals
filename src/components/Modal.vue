<template>
  <div class="backdrop" @click.self="closeModal" >
    <div class="modal">
      <slot></slot>
      <div class="actions">
        <slot name="links"></slot>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  methods: {
    closeModal(){
      this.$emit('close')
    }
  }
}
</script>
<style>
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background-color: white;
  border-radius: 10px;
  color: black;
}
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
.actions {
  display: flex;
  justify-content: center;
}
a {
  text-decoration: none;
  font-size: 24px;
  padding: 0.5rem 1rem;
  margin-right: 1rem;
  border: 1px solid transparent;
  border-radius: 4px;
  text-align: center;
  background-color: rgb(161, 64, 64);
  color: white;
}
a:hover {
  background-color: rgba(161, 64, 64, 0.8);
}
</style>