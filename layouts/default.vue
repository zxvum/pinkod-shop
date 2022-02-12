<template>
  <div>
    <header-component></header-component>

    <div class="page">
      <Nuxt />
    </div>
  </div>
</template>

<style lang="scss" scoped>
  .page{
    padding-top: 72px;
  }
  @media (min-width: 992px){
    .page{
      padding-top: 110px;
    }
  }
</style>

<script>
export default {

}
</script>
