<template>
  <div class="time">
    <div class="time__background" :class="timeBackgroundValue" style>
      <img :src="timeIconBackgroundValue" alt />
    </div>
    <div class="time__box">
      <div class="time__box__head">
        <p class="time__box__head--title">{{ data.timeframes.title }}</p>
        <img src="../assets/images/icon-ellipsis.svg" alt />
      </div>
      <div class="time__box__body">
        <p
          class="time__box__body__hours"
        >{{ timeSequence == 'daily' ? data.timeframes.daily.current : (timeSequence == 'weekly' ? data.timeframes.weekly.current : data.timeframes.monthly.current) }}hrs</p>
        <p
          class="time__box__body__last"
        >{{ timeSequence == 'daily' ? 'Hier' : (timeSequence == 'weekly' ? 'Dernière semaine' : 'Dernier mois') }} - {{ timeSequence == 'daily' ? data.timeframes.daily.previous : (timeSequence == 'weekly' ? data.timeframes.weekly.previous : data.timeframes.monthly.previous) }}hrs</p>
      </div>
    </div>
  </div>
</template>

<script>
import iconWork from '../assets/images/icon-work.svg';
import iconPlay from '../assets/images/icon-play.svg';
import iconStudy from '../assets/images/icon-study.svg';
import iconExercice from '../assets/images/icon-exercise.svg';
import iconSocial from '../assets/images/icon-social.svg';
import iconSelfCare from '../assets/images/icon-self-care.svg';
export default {
  name: 'TimeBox',
  props: ['data', 'timeSequence'],
  // data () {
  //   return {

  //   }
  // }
  computed: {
    timeBackgroundValue () {
      if (this.data.title == 'Travail') {
        return 'time__background--work';
      } else if (this.data.title == 'Jeux') {
        return 'time__background--play';
      } else if (this.data.title == 'Études') {
        return 'time__background--study';
      } else if (this.data.title == 'Sport') {
        return 'time__background--exercise';
      } else if (this.data.title == 'Social') {
        return 'time__background--social';
      } else {
        return 'time__background--selfcare';
      }
    },
    timeIconBackgroundValue () {
      if (this.data.title == 'Travail') {
        return iconWork;
      } else if (this.data.title == 'Jeux') {
        return iconPlay;
      } else if (this.data.title == 'Études') {
        return iconStudy;
      } else if (this.data.title == 'Sport') {
        return iconExercice;
      } else if (this.data.title == 'Social') {
        return iconSocial;
      } else {
        return iconSelfCare;
      }
    }
  }
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
      background: linear-gradient(var(--color-light-red-work) 20%, rgba(0, 0, 0, 0))
    &--play
      background: linear-gradient(var(--color-soft-blue-play) 20%, rgba(0, 0, 0, 0))
    &--study
      background: linear-gradient(var(--color-light-red-study) 20%, rgba(0, 0, 0, 0))
    &--exercise
      background: linear-gradient(var(--color-lime-green-exercise) 20%, rgba(0, 0, 0, 0))
    &--social
      background: linear-gradient(var(--color-violet-social) 20%, rgba(0, 0, 0, 0))
    &--selfcare
      background: linear-gradient(var(--color-orange-self-care) 20%, rgba(0, 0, 0, 0))
  &__box
    height: 201px
    width: 100%
    position: absolute
    bottom: 0
    background-color: var(--color-dark-blue)
    border-radius: 12px

    &:hover
      background-color: lighten(#1c1f4a, 15%)
    &__head
      width: 100%
      display: flex
      justify-content: space-between
      align-items: center
      &--title
        font-size: 0.9rem
        margin-left: 25px
        margin-top: 25px
    img
      margin-right: 25px
      margin-top: 13px
      cursor: pointer
    &__body
      margin-left: 25px
      &__hours
        font-size: 3.5rem
        margin-top: 1rem
        margin-bottom: 0
      &__last
        margin-top: 0.5rem
        font-size: 0.8rem
        color: var(--color-pale-Blue)
</style>