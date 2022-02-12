<template>
  <div>
    <button v-if="subcategories" @click="change" class="category">
      <p>{{ category }}</p>
      <svg-arrow :class="isOpen ? 'active' : ''"></svg-arrow>
    </button>
    <a href="#" v-else class="category">
      <p>{{ category }}</p>
    </a>

    <ul class="categories-list" :class="isOpen ? 'active' : ''" v-if="subcategories">
      <a href="#" class="subcategory" v-for="(item, index) in subcategories" :key="index">{{ item }}</a>
    </ul>
  </div>
</template>

<style lang="scss">
  .category{
    display: flex;
    align-items: center;
    gap: 10px;
    background: transparent;
    border: none;
    margin-bottom: 4px;
    font-size: 18px;

    svg{
      fill: $secondary;
      transition: 0.2s all;

      &.active{
        transform: rotate(180deg);
        fill: $primary;
      }
    }
  }

  .categories-list{
    display: flex;
    flex-direction: column;
    max-height: 0;
    opacity: 0;
    visibility: hidden;
    transition: 0.2s all;

    &.active{
      visibility: visible;
      opacity: 1;
      max-height: 81px;
    }

    .subcategory{
      color: $secondary;
      padding: 4px 0 4px 22px;
      font-size: 16px;
      transition: 0.2s all;
      border-radius: 4px;

      &:hover{
        background: $dark-light;
      }
    }
  }
</style>

<script>
export default {
  props: {
    category: String,
    subcategories: Array
  },
  data() {
    return{
      isOpen: false
    }
  },
  methods: {
    change() {
      this.isOpen = !this.isOpen
    }
  }
}
</script>
