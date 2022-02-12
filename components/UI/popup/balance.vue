<template>
  <popup-template>
    <div class="card-title">
      <p class="card-title__text">Название окна</p>
      <button @click="$emit('closePopup')" class="card-title__button">Закрыть</button>
    </div>
    <div class="card-content">
      <slot></slot>
    </div>
  </popup-template>
</template>

<style lang="scss">
  .card-title{
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
</style>
