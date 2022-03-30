<template>
    <main class="container-fluid px-5">
        <div v-for="(element, index) in albumList" :key="index" class="col-6 md-4 lg-3 mb-3">
            <Album :albumElement="element" />
        </div>
    </main>
</template>

<script>
import axios from "axios";
import Album from './Album.vue';

export default {
    name: "AlbumList",
    components: {
        Album,
    },
    data: function(){
        return {
            apiAlbum : "https://flynn.boolean.careers/exercises/api/array/music",
            albumList : null,
        }
    },
    created: function(){
        this.getAlbumList(this.apiAlbum);
        
    },
    methods: {
        getAlbumList(apiUrl){
        axios
        .get(apiUrl)
        .then((result) => {
            this.albumList = result.data.response;
            console.table(this.albumList);
        })
        .catch((error) => {
            console.error(error);
        })
        }
    },
}
</script>

<style>

</style>