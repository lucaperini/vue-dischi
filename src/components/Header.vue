<template>
<nav class="navbar navbar-light bg-dark">
    <div class="container">
        <a class="navbar-brand" href="#">
        <img src="../assets/spotify_icon.png" alt="main logo spotify">
        </a>
        <select 
            class="form-select" 
            aria-label="Default select example" 
            v-model="selectedGenre"
            @change="$emit('changedSelGenre', selectedGenre)"
            >
            <option selected value="">All</option>
            <option v-for="(genre, index) in genresList" :key="index" :value="genre"> {{ genre }}</option>
        </select>
    </div>
</nav>
</template>

<script>
export default {
    name: "HeaderIndex",
        props: {
        genresList : Array
        },
        data: function() {
            return{
                selectedGenre: '',
            }
        },
    
}
</script>

<style lang="scss" scoped>
.form-select{
    width:20%;
}
.container img {
    width:50px;
    height:50px;
}
</style>