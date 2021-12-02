<template>
  <div class="container">
    <!-- Profile -->
    <div class="profile">
      <img class="profile__image" :src="imageProfile" alt />
      <h1 class="profile__title">
        Report for
        <br />
        <span>Jeremy Robson</span>
      </h1>
    </div>
    <!-- Menu -->
    <div class="menu">
      <span class="menu__item" :class="active == 'daily' ? 'menu__item--active' : ''" @click="$emit('timeSequenceChanged', 'daily'); setActiveTo('daily')">Daily</span>
      <span class="menu__item" :class="active == 'weekly' ? 'menu__item--active' : ''" @click="$emit('timeSequenceChanged', 'weekly'); setActiveTo('weekly')">Weekly</span>
      <span class="menu__item" :class="active == 'monthly' ? 'menu__item--active' : ''" @click="$emit('timeSequenceChanged', 'monthly'); setActiveTo('monthly')">Monthly</span>
    </div>
  </div>
</template>

<script>
import imageProfile from '../assets/images/image-jeremy.png'
export default {
  name: 'ProfilMenu',
  data () {
    return {
      imageProfile: imageProfile,
      active: 'weekly',
    }
  },
  methods: {
    setActiveTo (timeSequence) {
      this.active = timeSequence
    }
  }
}
</script>

<style scoped lang="sass">

.container
  width: 240px
  background-color: var(--color-dark-blue)
  border-radius: 12px
  & .profile
    background-color: var(--color-blue)
    padding: 2.5rem 2rem 5rem
    border-radius: 12px
    &__image
      width: 70px
      border: 2px solid white
      border-radius: 99999px
      margin-bottom: 2rem
    &__title
      font-size: 0.8rem
      font-weight: 300
      > span
        font-size: 2.5rem
  & .menu
    display: flex
    flex-direction: column
    height: 150px
    justify-content: space-evenly
    background-color: var(--color-dark-blue)
    padding: 0 2rem
    border-radius: 12px
    &__item
      font-size: .9rem
      color: var(--color-desaturated-blue)
      cursor: pointer
      &:hover, &:active, &:focus
        color: white
      &--active
        color: white
</style>