<template>
  <div class="backdrop" @click.self="closePopup">
    <div class="card">
      <slot></slot>
    </div>
  </div>
</template>

<style lang="scss">
  .backdrop{
    width: 100vw;
    height: 100vh;
    position: fixed;
    z-index: 11;
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .card{
    width: 600px;
    background: $dark-light;
    border-radius: 15px;
    border: 1px solid $dark-border;
    padding: 20px;
  }
</style>

<script>
export default {
  methods: {
    closePopup(){
      this.$parent.$emit('closePopup')
    }
  }
}
</script>
