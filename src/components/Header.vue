<template>
<nav class="navbar navbar-light bg-dark">
    <div class="container">
        <a class="navbar-brand text-white" href="#">
        <img class="mr-2 fs-1" src="../assets/vynil.png" alt="main logo spotify"> VUENYL
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