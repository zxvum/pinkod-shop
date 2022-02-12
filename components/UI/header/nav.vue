<template>
  <nav class="nav">
    <NuxtLink class="nav-link" v-for="(item, index) in links" :key="index" :to="item.path" active-class="active">
      <component :is="item.component"/>
      <p>{{ item.content }}</p>
    </NuxtLink>
  </nav>
</template>

<script>
export default {
  data(){
    return{
      links: [
        {
          path: '/',
          content: 'Главная',
          component: 'svg-grid'
        },
        {
          path: '/blog',
          content: 'Блог',
          component: 'svg-globe'
        },
        {
          path: '/about',
          content: 'О нас',
          component: 'svg-question'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.nav{
  height: 100%;
  display: none;
  align-items: center;

  &-link{
    height: 100%;
    display: flex;
    align-items: center;
    gap: 5px;
    padding: 0 9px;
    transition: 0.2s all;

    &:hover{
      background: $dark-light;
    }

    svg{
      fill: $secondary;
    }
    p{
      color: $secondary;
    }
  }
  &-link.active{
    svg{
      fill: #ffffff;
    }
    p{
      color: #ffffff;
    }
  }
}
@media (min-width: 992px) {
  .nav{
    display: flex;
  }
  .nav-link{
    padding: 0 15px;
  }
}
</style>
