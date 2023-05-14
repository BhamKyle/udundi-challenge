<template>
  <div id="app">
    <HomeComponent/>
  </div>
</template>

<script>
import HomeComponent from './components/HomeComponent.vue'

export default {
  name: 'App',
  components: {
    HomeComponent
  }
}
</script>

<style>
  h1, h2 {
    font-family: 'Didot';
    font-style: normal;
  }

  h5 {
    font-family: Lato;
    font-style: normal;
  }

  p {
    font-family: Lato;
    font-size: 18px;
    font-weight: 400;
  }
</style>
