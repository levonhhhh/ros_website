<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import {ref} from 'vue'

const songs = ref([
  {name: 'Lovely Rita', file: 'src/assets/audio/smaller_MASTER Lovely Rita.mp3'},
  {name: 'Hey Jude', file: 'src/assets/audio/smaller_MASTER Hey Jude.mp3'},
  {name: 'Can\'t Help Falling in Love', file: 'src/assets/audio/smaller_MASTER Cant Help Falling in Love Cover.mp3'},
  {name: 'Nothing\'s Gonna Change My Love for You', file: 'src/assets/audio/smaller_MASTER Nothings Gonna Change my Love for You.mp3'},
  {name: 'Chamber of Reflection', file: 'src/assets/audio/smaller_MASTER Chamber of Reflection.mp3'},
  {name: 'Thriller', file: 'src/assets/audio/smaller_MASTER Thriller.mp3'},
  {name: 'Dancing Queen', file: 'src/assets/audio/smaller_MASTER Dancing Queen.mp3'},

])
</script>

<template>
  <header>


  </header>

  <body>
  <div id="main-grid"><div id = "left">
      <div id="bigName">
        <div id="ray">Ray</div>
        <div id="of">of</div>
        <div id="sun">Sun</div>
      </div>
    <div>
      <div id="logo"><img alt="Logo" src="./assets/Ray%20of%20Sun%20Logo.svg" width="120"/></div>


    </div>
    </div>
    <div id="right"><br><heading>About Us</heading><p>Hi, we're Ray of Sun, a two-person band consisting of <b>Ray</b>mond Chen and Tyler <b>Sun</b>.
      We're both in fourth year undergrad—Tyler's studying at McMaster University and Raymond's over at Queen's
      University.</p>
      <p>Both being volunteers at St. Joseph's Healthcare in Hamilton, we partnered up via our mutual love for music and
        started performing at the West 5th campus and recorded covers together during the summer of 2023.</p>
      <p>With Tyler behind the keys, and Raymond being a master of the alto sax, we've created some cool covers of
        classics from the past sixty years, from Elvis to the Beatles to Mac DeMarco.</p>
      <p>We're gearing up to play together again in summer 2024, so, keep an ear out for us if you're in Hamilton!</p>
      <heading>Release 1: Ray of Sun at West 5th</heading>
      <div id="cover"><img src="./assets/ray of sun cover 2  rendered.png" height="300" /></div>
      <li v-for="song in songs">
        <p>{{ song.name }}</p>
        <audio controls>
          <source :src=song.file type="audio/mpeg">
        </audio>
      </li>
    </div>
  </div>

  </body>

  <footer>

  </footer>
</template>

<style scoped lang="sass">

//header
//  #logo
//    position: absolute
//    left: random(500)
//    top: random(500)

body
  padding: 25px
  margin: 0
  background-color: lightgrey


@font-face
  font-family: officeTimes
  src: url(src/assets/fonts/OfficeTimesRound-Regular.otf)


@font-face
  font-family: weidemannBold
  src: url(src/assets/fonts/WeidemannStd-Bold.otf)


@font-face
  font-family: weidemann
  src: url(src/assets/fonts/WeidemannStd-Book.otf)


@mixin title
  font:
    family: officeTimes
    size: 144px
  line-height: 144px
  margin-bottom: 144px
  color: #272525

@mixin heading
  font:
    family: weidemannBold
    size: 24px
  line-height: 30px
  margin-bottom: 15px
  margin-top: 0px
  color: #272525

@mixin para
  font:
    family: weidemann
    size: 24px
  line-height: 30px
  margin-bottom: 15px
  margin-top: 0px
  color: #272525

#left
  #logo
    position: fixed
    bottom: 25px
    left: 25px
  #bigName
    @include title

    #ray
      text-align: left
    #of
      text-align: center
    #sun
      text-align: right
    @media (min-width: 600px)
      width: 47%
      position: fixed
      top: 25px
      left: 25px
#right
  p
    @include para
    display: block
  li
    list-style-type: none
  heading
    @include heading
  audio
    margin-bottom: 30px
  #cover
    float: right



@mixin two-column-flexbox
  display: flex
  flex-wrap: wrap
  justify-content: space-between

  > *
    flex: 0 0 48%

#main-grid
  @include two-column-flexbox

  @media (max-width: 600px)
    flex-direction: column

    > *
      flex: 0 0 100%

</style>
