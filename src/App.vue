<template>
  <div class="wrapper">
    <Header />
    <main class="main">
      <div class="container">
        <h1 class="hero__title title title--h1">Random beer me</h1>
        <user-profile />
        <recommend-beer />
      </div>
    </main>
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import UserProfile from './components/UserProfile.vue'
import RecommendBeer from './components/RecommendBeer.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Header,
    UserProfile,
    RecommendBeer,
    Footer
  }
}
</script>

<style lang="scss">
@import "./sass/mixins";
@import "./sass/variables";

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  width: 100%;
  min-height: 100vh;
  height: 100%;
}

#app {
  width: 100%;
  height: 100%;
  min-height: 100vh;
  font-size: 14px;
  line-height: 133%;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 0;
  @include vp-375 {
    font-size: 16px;
  }
  @include vp-576 {
    font-size: 18px;
  }
}

.wrapper {
  position: relative;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  width: 100%;
  height: 100%;
  min-height: 100vh;
  min-height: calc(100 * var(--vh, 1vh));
}

.main {
  padding: 75px 0 1em;
  flex: 1 1 auto;
  position: relative;
}

.container {
  width: 100%;
  max-width: 100%;
  padding: 0 16px;
  margin: 0 auto;
  @include vp-576 {
    max-width: 500px;
    padding: 0 24px;
  }
}

.title {
  margin: 0;
  padding: 0;
  font-size: 1em;
  line-height: 1.5em;
  font-weight: 700;
  text-transform: uppercase;
  @include vp-375 {
  }
  &--h1 {
    font-size: 1.5em;
  }
}

.hero {
  &__title {
    margin: 0.5em 0;
    text-align: center;
  }
}

</style>
