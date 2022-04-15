<template>
  <footer class="footer">
    <div class="container footer__container">
      <div class="footer__social">
        <a
          class="footer__social-icon"
          href="https://www.vk.com"
          target="_blank"
        >
          <img src="../assets/icons/icon-vk.svg" alt="Иконка vk" />
        </a>
        <a
          class="footer__social-icon"
          href="https://web.telegram.org/"
          target="_blank"
        >
          <img src="../assets/icons/icon-tg.svg" alt="Иконка telegram" />
        </a>
      </div>
      <div class="footer__copy">
        <span class="footer__copy-span">&copy; ООО "Дружная компания"</span>
        <span class="footer__copy-span">&nbsp;2022</span>
      </div>
    </div>
  </footer>
</template>
<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Footer'
}
</script>
<style lang="scss">
@import "../sass/mixins";
@import "../sass/variables";

.footer {
  width: 100%;
  min-height: 100px;
  padding: 1em 0;
  background-color: $color-default-black;
  flex-shrink: 0;
  &__social {
    display: flex;
    &-icon {
      flex: 0 0 32px;
      margin-right: 1em;
    }
  }
  &__copy {
    margin-top: 0.5em;
    color: $color-default-white;
  }
}
</style>
