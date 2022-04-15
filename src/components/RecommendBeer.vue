<template>
  <section class="recommend-beer">
    <div class="recommend-beer__btn-wrapper">
      <button class="btn recommend-beer__btn" @click="getRandomBeer">Какое будем сегодня?</button>
    </div>
    <div class="recommend-beer__desc">
      <ul class="recommend-beer__desc-list" v-for="beer in beerItems" :key="beer">
          <li class="recommend-beer__desc-list-item">
            <span class="recommend-beer__desc-list-item-property">марка: </span>
            <span class="recommend-beer__desc-list-item-value">{{ beer.brand }}</span>
          </li>
          <li class="recommend-beer__desc-list-item">
            <span class="recommend-beer__desc-list-item-property">название: </span>
            <span class="recommend-beer__desc-list-item-value">{{ beer.name }}</span>
          </li>
          <li class="recommend-beer__desc-list-item">
            <span class="recommend-beer__desc-list-item-property">стиль: </span>
            <span class="recommend-beer__desc-list-item-value">{{ beer.style }}</span>
          </li>
          <li class="recommend-beer__desc-list-item">
            <span class="recommend-beer__desc-list-item-property">содержание спирта: </span>
            <span class="recommend-beer__desc-list-item-value">{{ beer.alcohol }}</span>
          </li>
          <li class="recommend-beer__desc-list-item">
            <span class="recommend-beer__desc-list-item-property">blg: </span>
            <span class="recommend-beer__desc-list-item-value">{{ beer.blg }}</span>
          </li>
          <li class="recommend-beer__desc-list-item">
            <span class="recommend-beer__desc-list-item-property">солод: </span>
            <span class="recommend-beer__desc-list-item-value">{{ beer.malts }}</span>
          </li>
          <li class="recommend-beer__desc-list-item">
            <span class="recommend-beer__desc-list-item-property">дрожжи: </span>
            <span class="recommend-beer__desc-list-item-value">{{ beer.yeast }}</span>
          </li>
      </ul>
    </div>
  </section>
</template>

<script>
const getBeer = {
  data () {
    return {
      urlBeer: 'https://random-data-api.com/api/beer/random_beer',
      beerItems: [],
      errors: []
    }
  },
  methods: {
    async getRandomBeer () {
      try {
        const response = await fetch(this.urlBeer)
        const result = await response.json()
        this.beerItems = []
        this.beerItems.push(result)
        // console.log(this.beerItems)
      } catch (error) {
        this.errors.push()
        console.log(this.errors)
      }
    }
  },
  mounted () {
  }
}
export default getBeer
</script>

<style scoped lang="scss">
@import "../sass/mixins";
@import "../sass/variables";
@import "../sass/btn";

.recommend-beer {
  &__btn-wrapper {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  &__btn {
    background-color: $color-moon-yellow;
    font-size: 1em;
    text-transform: uppercase;
    margin: 2em 0;
    border-radius: 5px;
    max-width: 300px;
  }
  &__desc {
    margin: 0.5em 0;
    padding: 1em 0;
    min-height: 80px;
    &-list {
      list-style: none;
      &-item {
        display: flex;
        justify-content: space-between;
        &-property {
          font-weight: 700;
        }
      }
    }
  }
}
</style>
