<template>
  <div class="backdrop" @click.self="closeSlider">
    <div class="slider">

      <slot></slot>

    </div>
  </div>
</template>

<style lang="scss" scoped>
.backdrop{
  display: none;
  position: fixed;
  z-index: 10;
  width: 100vw;
  height: calc(100vh - 52px);
  top: 52px;
  background: rgba(0, 0, 0, 0.5);
  transition: 0.2s all;
}

.backdrop.active{
  .slider{
    transform: translateX(0%);
  }
}

@media (min-width: 576px){
  .backdrop{
    display: block;
  }
}
@media (min-width: 992px){
  .backdrop{
    display: none;
  }
}
</style>

<script>
export default {
  methods: {
    closeSlider() {
      this.$emit('closeSlider')
    }
  },
  emits: {
    closeSlider: null
  }
}
</script>
