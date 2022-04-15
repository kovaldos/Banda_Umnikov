<template>
  <section class="user-profile">
    <div class="user-profile__wrapper" v-for="user in users" :key="user">
      <div class="user-profile__pic">
        <img :src="user.avatar" alt="user avatar" class="user-profile__img">
      </div>
      <ul class="user-profile__list">
        <li class="user-profile__list-item">
          <span class="recommend-beer__desc-list-item-property">Имя: </span>
          <span class="recommend-beer__desc-list-item-value">{{ user.first_name }} </span>
        </li>
        <li class="user-profile__list-item">
          <span class="recommend-beer__desc-list-item-property">Возраст: </span>
          <span class="recommend-beer__desc-list-item-value">{{ user.current_age }}</span>
        </li>
        <li class="user-profile__list-item">
          <span class="recommend-beer__desc-list-item-property">Должность: </span>
          <span class="recommend-beer__desc-list-item-value">{{ user.employment.title }} </span>
        </li>
      </ul>
    </div>
  </section>
</template>
<script>
export default {
  data () {
    return {
      urlUser: 'https://random-data-api.com/api/users/random_user',
      users: [],
      errors: []
    }
  },
  methods: {
    async getRandomUser () {
      const response = await fetch(this.urlUser)
      const result = await response.json()
      try {
        this.users = []
        this.users.push(result)
        this.users.forEach(function (user) {
          const birthDate = new Date(user.date_of_birth)
          const today = new Date()
          const userAge = today.getFullYear() - birthDate.getFullYear()
          user.current_age = userAge
        })
        // console.log(this.users)
      } catch (error) {
        this.errors.push()
        console.log(this.errors)
      }
    }
  },
  mounted () {
    this.getRandomUser()
  }
}
</script>
<style lang="scss">
@import "../sass/mixins";
@import "../sass/variables";
@import "../sass/btn";
.user-profile {
  &__wrapper {
    display: flex;
    justify-content: flex-start;
    max-width: 450px;
    gap: 1em;
    min-height: 150px;
    padding: 1em 0;
  }
  &__pic {
    flex: 0 0 100px;
    height: 100px;
    border-radius: 5px;
    overflow: hidden;
    border: 1px solid rgba($color-default-black, 0.2);
  }
  &__img {
    width: 100%;
    height: auto;
    object-fit: cover;
    vertical-align: top;
  }
  &__list {
    list-style: none;
  }
}
</style>
