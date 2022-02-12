<template>
  <button @click="openSlider" class="header-button">
    <div class="content" :class="isOpenSlider ? 'active' : ''">
      <span></span>
      <span></span>
      <span></span>
    </div>
  </button>
</template>

<style lang="scss">
.header-button {
  background: transparent;
  border: none;
  position: relative;
  display: none;
  justify-content: center;
  align-items: center;

  .content {
    width: 30px;
    height: 22px;
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;

    span {
      position: absolute;
      right: 0;
      width: 30px;
      height: 3px;
      background: $secondary;
      border-radius: 2px;
      visibility: visible;
      opacity: 1;
      transition: 0.2s all;

      &:first-child {
        margin-bottom: 16px;
      }

      &:last-child {
        margin-top: 16px;
      }
    }

    &:hover span {
      &:first-child {
        width: 16px;
      }

      &:last-child {
        width: 24px;
      }
    }

    &.active {
      &:hover span {
        width: 30px;
      }

      span {
        &:nth-child(2) {
          visibility: hidden;
          opacity: 0;
        }

        &:first-child {
          transform: rotate(45deg);
          margin: 0;
        }

        &:last-child {
          transform: rotate(-45deg);
          margin: 0;
        }
      }
    }
  }
}
@media (min-width: 576px) {
  .header-button{
    display: flex;
  }
}
@media (min-width: 992px) {
  .header-button{
    display: none;
  }
}
</style>

<script>
export default {
  methods: {
    openSlider(){
      this.$parent.$emit('openSlider')
    }
  },
  props: {
    isOpenSlider: {
      type: Boolean,
      default: false
    }
  }
}
</script>
