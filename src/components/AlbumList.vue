<template>
    <main>
        <div class="container p-5 gap-1">
            <div class="d-flex row row-cols-5">
                <div 
                    v-for="(element, index) in albumList" 
                    :key="index" class="d-inline-block">
                    <Album :albumElement="element" />
                </div>
            </div>
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

<style lang="scss" scoped>

main {
    background-color: rgb(33, 44, 58);
    height: 100%
}
.container {
    max-width:1000px;
}

</style>