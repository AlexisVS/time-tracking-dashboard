<template>
  <div id="app">
    <div class="wrapper">
      <div class="container">
        <ProfilMenu class="profile_menu" @timeSequenceChanged="updateTimeSequence"/>
        <TimeBox v-for="data in timeData" :data="data" :timeSequence="timeSequence" :key="data.title"   />
      </div>
    </div>
  </div>
</template>

<script>
import ProfilMenu from './components/ProfilMenu.vue';
import TimeBox from './components/TimeBox.vue';
import timeData from '../exo-ressources/data.json'
export default {
  name: 'App',
  components: {
    ProfilMenu,
    TimeBox,
  },
  data () {
    return {
      timeSequence: 'weekly',
      timeData: timeData,
    }
  },
  methods: {
    updateTimeSequence (sequence) {
      console.log(sequence);
      this.timeSequence = sequence
    }
  },
  watch: {}
}
</script>

<style lang="sass">

@font-face
  font-family: 'Rubik',sans-serif
  src: url('./assets/fonts/Rubik-Light.ttf') format('ttf')
  font-weight: 300
  font-display: swap

  @font-face
    font-family: 'Rubik',sans-serif
    src: url('./assets/fonts/Rubik-Regular.ttf') format('ttf')
    font-weight: 400
    font-display: swap

  @font-face
    font-family: 'Rubik',sans-serif
    src: url('./assets/fonts/Rubik-Medium.ttf') format('ttf')
    font-weight: 500
    font-display: swap

// Primary
$blue: hsl(246, 80%, 60%)
$light-red-work: hsl(15, 100%, 70%)
$soft-blue-play: hsl(195, 74%, 62%)
$light-red-study: hsl(348, 100%, 68%)
$lime-green-exercise: hsl(145, 58%, 55%)
$violet-social: hsl(264, 64%, 52%)
$orange-self-care: hsl(43, 84%, 65%)
// Neutral
$very-dark-blue: hsl(226, 43%, 10%)
$dark-blue: hsl(235, 46%, 20%)
$desaturated-blue: hsl(235, 45%, 61%)
$pale-Blue: hsl(236, 100%, 87%)

:root
  --color-blue: #{$blue}
  --color-light-red-work: #{$light-red-work}
  --color-soft-blue-play: #{$soft-blue-play}
  --color-light-red-study: #{$light-red-study}
  --color-lime-green-exercise: #{$lime-green-exercise}
  --color-violet-social: #{$violet-social}
  --color-orange-self-care: #{$orange-self-care}
  --color-very-dark-blue: #{$very-dark-blue}
  --color-dark-blue: #{$dark-blue}
  --color-desaturated-blue: #{$desaturated-blue}
  --color-pale-Blue: #{$pale-Blue}

body
  margin: 0

#app
  font-family: 'Rubik', sans-serif
  font-weight: 300
  font-size: 18px
  min-height: 100vh
  width: 100%
  background: $very-dark-blue
  display: flex
  flex-direction: column
  justify-content: center
  align-items: center
  color: white
  font-weight: 300

  > .wrapper
    width: 100%
    display: flex
    flex-direction: column
    justify-content: center
    align-items: center
    > .container
      padding-top: 25px
      padding-bottom: 25px
      height: 500px
      display: grid
      // align-items: stretch
      grid-template-columns: repeat(4, 1fr)
      grid-template-rows: repeat(2, 1fr)
      grid-gap: 25px

      > .profile_menu
        grid-column: 1/2
        grid-row: 1/3
</style>
