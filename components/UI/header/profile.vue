<template>
  <button class="profile">
    <img src="https://via.placeholder.com/150" alt="avatar">
    <svg-arrow></svg-arrow>
  </button>
</template>

<style lang="scss" scoped>
.profile{
  height: 100%;
  display: none;
  align-items: center;
  gap: 5px;
  background: transparent;
  border: none;
  cursor: pointer;
  padding: 0 5px;
  transition: 0.2s all;

  img{
    width: 40px;
    height: 40px;
    -webkit-border-radius: 50%;
    -moz-border-radius: 50%;
    border-radius: 50%;
  }
  svg{
    transition: 0.2s all;
    fill: $secondary;

    &.active{
      transform: rotate(90deg);
      fill: $primary;
    }
  }
  &:hover{
    background: $dark-light;
  }
}
@media (min-width: 992px) {
  .profile{
    display: flex;
  }
}
</style>
