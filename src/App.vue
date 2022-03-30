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

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
