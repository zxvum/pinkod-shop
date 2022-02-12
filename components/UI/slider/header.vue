<template>
  <slider-template @closeSlider="closeSlider">
    <div class="slider-head">
      <p class="slider-head__title">Фильтры</p>
      <button @click="closeSlider" class="slider-head__close">Закрыть</button>
    </div>
    <input v-model.lazy="filters.search" type="text" placeholder="Поиск..." class="slider-search">
    <div class="slider-categories">
      <slider-category v-for="(item, index) in links" :key="index" :category="item.category" :subcategories="item.subcategories"></slider-category>
    </div>
    <div class="price-picker">
      <div class="from">
        <label for="from">Цена от:</label>
        <input v-model.lazy="filters.price.from" id="from" type="number" placeholder="120">
      </div>
      <div class="to">
        <label for="to">Цена до:</label>
        <input v-model.lazy="filters.price.to" id="to" type="number" placeholder="1300">
      </div>
    </div>
    <div class="slider-type">
      <label for="stock">
        <input type="radio" name="type" id="stock" checked hidden>
        <span></span>
        <p>В наличии</p>
      </label>
      <label for="order">
        <input type="radio" name="type" id="order" checked hidden>
        <span></span>
        <p>Под заказ</p>
      </label>
    </div>
  </slider-template>
</template>

<style lang="scss">
.slider{
  width: 350px;
  height: 100%;
  background: $dark;
  border-right: 2px solid $dark-border !important;
  transition: .2s ease-in-out;

  display: flex;
  flex-direction: column;
  gap: 28px;
  padding: 20px 25px !important;

  transform: translateX(-100%);
}

.slider-head{
  display: flex;
  align-items: center;
  justify-content: space-between;

  &__title{
    position: relative;
    font-weight: 500;
    font-size: 18px;
    line-height: 20px;
    display: flex;
    justify-content: center;
    align-items: flex-end;

    &:after{
      content: "";
      position: absolute;
      width: 90%;
      height: 2px;
      background: $secondary;
      transform: translateY(5px);
    }
  }
  &__close{
    padding: 8px 22px;
    background: transparent;
    border: 2px solid $dark-light;
    -webkit-border-radius: 8px;
    -moz-border-radius: 8px;
    border-radius: 8px;
    color: $secondary;

    transition: 0.2s all;

    &:hover{
      color: $white;
      background: $dark-light;
    }
  }
}
.slider-search{
  padding: 18px 30px;
  border-radius: 15px;
  font-size: 16px;
  border: none;
  background: $dark-light;
  color: $white;
}
.slider-categories{
  display: flex;
  flex-direction: column;
  gap: 14px;
}
.price-picker{
  display: flex;
  justify-content: space-between;

  .from, .to{
    display: flex;
    flex-direction: column;
    gap: 5px;

    input{
      width: 82px;
      height: 44px;
      color: $white;
      background: $dark-light;
      -webkit-border-radius: 15px;
      -moz-border-radius: 15px;
      border-radius: 15px;
      border: none;
      text-align: center;
    }
  }
}
.slider-type{
  display: flex;
  gap: 10px;
  flex-direction: column;
  justify-content: center;

  label{
    display: flex;
    gap: 10px;


    span{
      width: 22px;
      height: 22px;
      border-radius: 50%;
      border: 1px solid $dark-light;
    }

    input:checked + span {
      background-image: url('./assets/images/svg/checked.svg');
      background-position: top;
      border: none;
    }
  }
}
</style>

<script>
export default {
  data(){
    return{
      filters: {
        search: "",
        price: {
          from: null,
          to: null
        },
      },
      links: [
        {
          category: "Все категории"
        },
        {
          category: "Armored Warfare",
          subcategories: ['Подарки', 'Валюта', 'Премиум-статус']
        },
        {
          category: "Warface",
          subcategories: ['Подарки', 'Валюта', 'Премиум-статус']
        }
      ]
    }
  },
  methods: {
    closeSlider(){
      this.$emit('closeSlider')
    }
  },
  emits: {
    closeSlider: null
  }
}
</script>
