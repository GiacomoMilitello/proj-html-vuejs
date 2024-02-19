<script>
// import

export default {
  name: "NavBar",
  data() {
        return {
            revImages: [
                { url: 'src/img/h3-rev-img-1.png' },
                { url: 'src/img/h3-rev-img-2.png' },
                { url: 'src/img/h3-rev-img-3.png' },
                { url: 'src/img/h3-rev-img-4.png' },
                { url: 'src/img/h3-rev-img-5.png' },
                { url: 'src/img/h3-rev-img-6.png' }
            ]
        };
    }
};
</script>

<template>
  <div id="nav-bar">
    <ul class="w-75 mx-auto d-flex justify-content-between">
        <li>BOTTONE</li>
        <li>
            <li>
                PROPS
            </li>
        </li>
        <li>
            <li>
                buy PROPS
            </li>
        </li>
    </ul>

    <div id="carouselExampleRide" class="carousel slide carousel-fade" data-bs-ride="true">
  <div class="carousel-inner">
    <div class="carousel-item" v-for="(image, index) in revImages" :key="index" :class="{ active: index === 0 }">
      <figure class="w-25 mx-auto">
        <img :src="image.url" class="d-block w-100 img-fluid" alt="...">
      </figure>
    </div>
  </div>
  <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleRide" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleRide" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>
  </div>
</template>

<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;

#nav-bar {
  background-color: $dark-gray;
  background-image: url(../../img/cielostellato.PNG);
  @include bg-cover;
  color: $white;
}
</style>