<template>
  <div id="app">
    <section class="hero is-primary is-medium">
      <router-view></router-view>

      <div class="hero-foot">
        <div class="columns is-mobile">
          <div v-for="movieChoice in movieChoices" 
          class="column">
            <router-link :to="`/${movieChoice.id}`" 
                          tag="li"
                          class="movie-choice">
              <i :class="[{ 'fa fa-check-circle favorite-check': movieChoice.favorite }]" aria-hidden="true"></i> 
              <img :src="`${movieChoice.smallImgSrc}`"
              class="desktop"/>
                <p class="mobile movie-title">{{ movieChoice.subtitle }}</p>
            </router-link>
          </div>
        </div>
      </div>
    </section>
    <p class="appreciation-tag">
      Inspired by VueFlix <a href="https://medium.com/hackernoon/building-a-movie-app-interface-with-vue-js-cdc8aeb5db0b" target="_blank">Hassan Djirdeh</a>
    </p>
    <a href="https://twitter.com/tomateg06" target="_blank" class="twitter-section">
      <i class="fa fa-twitter-square" aria-hidden="true"></i>
    </a>
  </div>
</template>

<script>
import { MOVIES } from './assets/mock/movies'
export default {
  name: 'App',
    data () {
      return {
        movieChoices : MOVIES
      }
    },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
