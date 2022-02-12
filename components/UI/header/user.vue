<template>
  <div class="user">
    <header-balance></header-balance>
    <header-profile></header-profile>
    <header-burger :isOpenSlider="isOpenSlider"></header-burger>
  </div>
</template>

<style lang="scss" scoped>
  .user{
    height: 100%;
    display: flex;
    align-items: center;
    gap: 10px;
  }
</style>

<script>
export default {
  props: {
    isOpenSlider: {
      type: Boolean,
      default: false
    }
  }
}
</script>
