<template>
  <div class="balance">
    <button @click="openPopup" class="balance__button">
      <svg-plus></svg-plus>
    </button>
	<div class="balance__info">
    <svg width="14" height="14" viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M6.99998 5.83329C9.31931 5.83329 11.6666 5.03179 11.6666 3.49996C11.6666 1.96813 9.31931 1.16663 6.99998 1.16663C4.68065 1.16663 2.33331 1.96813 2.33331 3.49996C2.33331 5.03179 4.68065 5.83329 6.99998 5.83329Z"/>
      <path d="M2.33331 5.83329C2.33331 7.36512 4.68065 8.16662 6.99998 8.16662C9.31931 8.16662 11.6666 7.36512 11.6666 5.83329V4.66663C11.6666 6.19846 9.31931 6.99996 6.99998 6.99996C4.68065 6.99996 2.33331 6.19846 2.33331 4.66663V5.83329Z"/>
      <path d="M2.33331 8.16667C2.33331 9.6985 4.68065 10.5 6.99998 10.5C9.31931 10.5 11.6666 9.6985 11.6666 8.16667V7C11.6666 8.53183 9.31931 9.33333 6.99998 9.33333C4.68065 9.33333 2.33331 8.53183 2.33331 7V8.16667Z"/>
      <path d="M2.33331 10.5C2.33331 12.0319 4.68065 12.8334 6.99998 12.8334C9.31931 12.8334 11.6666 12.0319 11.6666 10.5V9.33337C11.6666 10.8652 9.31931 11.6667 6.99998 11.6667C4.68065 11.6667 2.33331 10.8652 2.33331 9.33337V10.5Z"/>
    </svg>
    <p>2023</p>
  </div>
  </div>
</template>

<style lang="scss" scoped>
.balance{
  background: $dark-light;
  height: 30px;
  border-radius: 8px;
  padding: 4px 17px 4px 5px;
  gap: 13px;
  display: flex;
  align-items: center;

  &__button{
    width: 22px;
    height: 100%;
    background: $primary;
    -webkit-border-radius: 8px;
    -moz-border-radius: 8px;
    border-radius: 8px;
    border: none;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;

    svg{
      width: 12px;
      height: 12px;
      fill: $white;
    }
  }
  &__info{
    display: flex;
    align-items: center;
    gap: 5px;

    svg{
      fill: $white;
      width: 14px;
      height: 14px;
    }
  }
}
@media (min-width: 992px) {
  .balance{
    height: 40px;
    padding: 5px 30px 5px 5px;
    border-radius: 15px;

    &__button{
      width: 30px;
      border-radius: 10px;
      transition: 0.2s all;

      &:hover{
        background: $primary-hover;
      }

      svg{
        width: 16px;
        height: 16px;
      }
    }
  }
}
</style>

<script>
export default {
  methods: {
    openPopup() {
      this.$parent.$emit('openPopup')
    }
  },
  emits: {
    openPopup: null
  }
}
</script>
