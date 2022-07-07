<template>
  <div class="container">
    <div class="d-flex row">
      <div class="col-12 text-center pb-3">
        <div class="card rounded">
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
  height: 350px;
  padding-bottom: 0.5rem;
  transition: border 1s ease-in-out;
  width: 14rem;
}

.card:hover {
  border: 1px solid rgba(255, 255, 255, 0.5);
  padding-bottom: 0.5rem;
  box-shadow: 0px 0px 10px 0px rgba(255, 255, 255, 0.3);
}

.card-body {
  padding: 0.2rem;
  margin-left: 0;
}
.card-body h5 {
  padding: 0.3rem;
  font-size: 1rem;
}

h5 {
  color: white;
  text-transform: uppercase;
  line-height: 1.3rem;
  font-weight: bold;
  font-size: 1.2rem;
}

.card-title h5 {
  line-height: 1.2rem;
}

p {
  line-height: 0.3em;
  font-size: 0.6rem;
  color: white;
  margin-right: 10px;
}
</style>
