<template>
  <header class="header">
    <div class="container header__container">
      <div class="header__logo">
        <a class="header__logo-link" href="#"
          ><img
            class="header__logo-img"
            src="https://pngicon.ru/file/uploads/pivo-128x128.png"
            alt="Иконка пиво"
        /></a>
      </div>
      <!-- <button class="btn header__btn">Войти</button> -->
    </div>
  </header>
</template>
<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Header'
}
</script>
<style lang="scss">
@import "../sass/mixins";
@import "../sass/variables";
@import "../sass/btn";

.header {
  width: 100%;
  position: fixed;
  min-height: 75px;
  background-color: $color-default-black;
  z-index: 10;
  flex-shrink: 0;
  &__container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    z-index: 10;
  }
  &__logo {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 0.5em;
    max-width: 70px;
    &-link {
      display: inline-block;
    }
    &-img {
      width: 100%;
      height: auto;
      object-fit: cover;
    }
  }
  &__btn {
    max-width: 100px;
    background-color: $color-moon-yellow;
    border-radius: 5px;
  }
}
</style>
