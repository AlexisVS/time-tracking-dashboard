<template>
  <div class="time">
    <div class="time__background time__background--work" style>
      <img src="../assets/images/icon-work.svg" alt="">
    </div>
    <div class="time__box">
      <div class="time__box__head">
        <p class="time__box__head--title">{{time.title}}</p>
        <img src="../assets/images/icon-ellipsis.svg" alt="">
      </div>
      <div class="time__box__body"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TimeBox',
}
</script>

<style scoped lang="sass">

.time
  width: 240px
  height: 240px
  position: relative
  border-radius: 12px
  &__background
    height: 100%
    width: 100%
    border-radius: 12px
    overflow: hidden
    display: flex
    justify-content: end
    > img
      object-fit: cover
      width: 65px
      height: 65px
      position: relative
      bottom: 9px
      right: 15px
    &--work
      background: linear-gradient(var(--color-light-red-work) 50%, rgba(0, 0, 0, 0))
      &--play
        background: linear-gradient(var(--color-soft-blue-play) 50%, rgba(0, 0, 0, 0))
      &--study
        background: linear-gradient(var(--color-light-red-study) 50%, rgba(0, 0, 0, 0))
      &--exercise
        background: linear-gradient(var(--color-lime-green-exercise) 50%, rgba(0, 0, 0, 0))
      &--social
        background: linear-gradient(var(--color-violet-social) 50%, rgba(0, 0, 0, 0))
      &--selfcare
        background: linear-gradient(var(--color-orange-self-care) 50%, rgba(0, 0, 0, 0))
  &__box
    height: 201px
    position: absolute
    bottom: 0
    background-color: var(--color-dark-blue)
    border-radius: 12px
    padding: 25px
    &:hover
      background-color: lighten(#1c1f4a, 15%)
    &__head
      width: 100%
      display: flex
      justify-content: space-between
      align-items: center
      &--title
        font-size: 0.8rem
</style>