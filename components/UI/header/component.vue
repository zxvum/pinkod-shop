<template>
	<div>
    <header class="header">
      <div class="container header__wrapper">
        <header-logo></header-logo>
        <header-nav></header-nav>
        <header-user @openSlider="openSlider()" :isOpenSlider="showSlider" @openPopup="openPopup"></header-user>
      </div>
    </header>

    <transition name="fade">
      <slider-header :class="showSlider ? 'active' : ''" v-show="showSlider" @closeSlider="closeSlider()"></slider-header>
    </transition>

    <transition name="fade">
      <popup-balance v-show="showPopup" @closePopup="closePopup" @openPopup="openPopup"></popup-balance>
    </transition>
  </div>
</template>

<style lang="scss">
	.header{
    position: fixed;
    width: 100%;
		height: 52px;
		background: $dark;
    border-bottom: 2px solid $dark-border;

		&__wrapper{
			height: 100%;
			display: flex;
			justify-content: space-between;
			align-items: center;
		}
	}
  @media (min-width: 992px){
    .header{
      height: 80px;
    }
  }

  .fade-enter-active, .fade-leave-active {
    transition: opacity .3s;
  }
  .fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
    opacity: 0;
  }
</style>

<script>
	export default {
    data(){
      return{
        showSlider: false,
        showPopup: false
      }
    },
    methods: {
      openSlider(){
        this.showSlider = !this.showSlider
      },
      closeSlider(){
        this.showSlider = false
      },

      closePopup(){
        this.showPopup = false
      },
      openPopup(){
        this.showPopup = !this.showPopup
      }
    },
	}
</script>
