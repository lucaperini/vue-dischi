<template>
  
    <div class="container p-5">
      <div class="row row-cols-3">
        
      
        <Album
          class="album"
          v-for="(element, index) in filteredDiscsList"
          :key="index"
          :albumElement="element"
        />
    
            
    
        
      </div>
    </div>
  
</template>
<script>
import axios from "axios";
import Album from "./Album.vue";

export default {
  name: "AlbumList",
  props: ["selectedGenre"],
  components: {
    Album,
  },
  data: function () {
    return {
      albumList: null,
      genresList: [],
    };
  },

  computed: {
    filteredDiscsList() {
      if (this.selectedGenre === "") {
        return this.albumList;
      }
      return this.albumList.filter(
        (element) => element.genre === this.selectedGenre
      );
    },
  },

  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((result) => {
        this.albumList = result.data.response;

        this.albumList.forEach((discElement) => {
          if (!this.genresList.includes(discElement.genre)) {
            this.genresList.push(discElement.genre);
          }
        });
        this.$emit("loadedGenres", this.genresList);
      })
      .catch((error) => {
        console.error(error);
      });
  },
};
</script>

<style lang="scss" scoped>

.container {
    max-width:800px;
    display: flex;
    direction: row;
    flex-wrap: wrap;
    
}

.album {
    margin-left:0;
}


</style>
