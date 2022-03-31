<template>
  <div id="app">
    <Header />
    <AlbumList />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import AlbumList from './components/AlbumList.vue'

export default {
  name: 'App',
  components: {
    Header,
    AlbumList,
  }
}
</script>

<style lang="scss">
@import './assets/scss/style.scss';
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@600;700&display=swap');

#app {
  font-family: 'Open Sans', Helvetica, Arial, sans-serif;
}
</style>
