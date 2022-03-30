<template>
    <div class="container-fluid">
        <img class="img-fluid" :src="albumElement.poster" :alt="albumElement.title">
        <h3>{{albumElement.title}}</h3>
        <p>{{albumElement.author}}</p>
        <p>{{albumElement.year}}</p>
    </div>
</template>

<script>
export default {
    name: 'AlbumObject',
    props: {'albumElement' : Object},
}
</script>
<style lang="scss" scoped>

</style>