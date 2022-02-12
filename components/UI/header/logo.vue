<template>
	<a href="#" class="logo">
    <img src="https://via.placeholder.com/150" alt="logo">
    <p>Pinkod-shop.ru</p>
	</a>
</template>

<style lang="scss" scoped>
  .logo{
    height: 100%;
    display: flex;
    align-items: center;
    gap: 10px;

    img{
      width: 30px;
      height: 30px;
      border-radius: 50%;
    }
  }
  @media (min-width: 768px){
    .logo p{
      font-size: 18px;
    }
  }
</style>
