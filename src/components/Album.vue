<template>
    <div class="container">
        <div class="row">
            <div class="col-md-6 text-center pb-3">
                <div class="card" style="width:10rem;">
                    <img class="card-img-top p-3" :src="albumElement.poster" :alt="albumElement.title">
                    <div class="card-body">
                        <h5 class="card-title text-center">{{albumElement.title}}</h5>
                        <p class="card-text d-inline-block">{{albumElement.author}}</p>
                        <p class="small-text">{{albumElement.year}}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>  
</template>
<script>
export default {
    name: 'AlbumObject',
    props: {'albumElement' : Object},
}
</script>
<style lang="scss" scoped>

.card {
    background-color: rgb(48, 58, 69) ;
    border-radius:0;
    height:310px;
    
}
.card-body {
    padding:.2rem;
}
.card-body h5{
    padding:.3rem;
    
}
h5{
    color:white;
    text-transform: uppercase;
    line-height:1.2rem;
    font-weight:bold;
    font-size: 1.2rem;
}
p {
    line-height:.1rem;
    font-size:.7rem;
    color:darkgray;
}
</style>