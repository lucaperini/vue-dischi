<template>
  <div id="app">
    <Header :genresList="genresList" @changedSelGenre="updateSelectedGenres" />
    <AlbumList :selectedGenre="selectedGenre" @loadedGenres="updateGenresList" />
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
  },
  data: function(){
    return{
      genresList : [],
      selectedGenre : '',
    }
  },
  methods: {
    updateGenresList(genresList){
      this.genresList = genresList;
    },
    updateSelectedGenres(selectedGenre){
      this.selectedGenre = selectedGenre;
    },
  }

}
</script>

<style lang="scss">
@import './assets/scss/style.scss';
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@600;700&display=swap');
#app {
  font-family: 'Open Sans', Helvetica, Arial, sans-serif;
}
body {
  background-color: rgb(33, 44, 58);  
}
</style>
