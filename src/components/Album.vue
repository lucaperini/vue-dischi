<template>
  <div class="container">
    <div class="row flex-column">
      <div class="col-12 text-center pb-3">
        <div class="card rounded" style="width: 14rem">
          <img
            class="card-img-top p-3"
            :src="albumElement.poster"
            :alt="albumElement.title"
          />

          <div class="card-body">
            <p class="fs-6 text-center text-white">
              {{ albumElement.author }}
            </p>
            <h5 class="card-title text-center text-warning">
              {{ albumElement.title }}
            </h5>
            <p class="small-text badge bg-success p-2">
              {{ albumElement.year }}
            </p>
            <p class="small-text badge bg-success p-2">
              {{ albumElement.genre }}
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "AlbumObject",
  props: { albumElement: Object },
};
</script>
<style lang="scss" scoped>
.card {
  background-color: rgb(48, 58, 69);
  height: 380px;
  padding-bottom: 0.5rem;
}
.card-body {
  padding: 0.2rem;
}
.card-body h5 {
  padding: 0.3rem;
  font-size: 1.3rem;
}
h5 {
  color: white;
  text-transform: uppercase;
  line-height: 1.3rem;
  font-weight: bold;
  font-size: 1.2rem;
}
.card-title h5 {
  line-height: 0.8rem;
}

p {
  line-height: 0.3em;
  font-size: 0.6rem;
  color: white;
  margin-right: 10px;
}
</style>
