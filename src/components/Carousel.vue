<script>
export default {
  name: "Carousel",
  props: {
    images: {
      type: Array,
      required: true
    },
    backgrounds: {
      type: Array,
      required: true
    }
  }
};
</script>

<template>

    <div id="carouselExampleRide" class="carousel slide carousel-fade" data-bs-ride="true">
  <div class="carousel-inner">
    <div class="carousel-item" v-for="(image, index) in images" :key="index" :class="{ active: index === 0 }">
      <div id="back" :style="{ backgroundImage: 'url(' + image.back + ')' }">
        <figure class="w-25 mx-auto d-flex justify-content-center ">
        <img :src="image.img" class="d-block w-100 img-fluid" alt="Image">
      </figure>
      </div>
    </div>
  </div>
  <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleRide" data-bs-slide="prev">

    <div class="arrow arrow-prev" aria-hidden="true">
        <div class="prev"></div>
    </div>

    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleRide" data-bs-slide="next">

    <div class="arrow arrow-next" aria-hidden="true">
        <div class="next"></div>
    </div>

    <span class="visually-hidden">Next</span>
  </button>
</div>

</template>

<style lang="scss" scoped>
@use "../styles/partials/variables" as *;
@use "../styles/partials/mixins" as *;

#carouselExampleRide{
  #back{
    @include bg-contain;
  }
  img{
    max-width: 280px
  }
  .carousel-control-prev{
    justify-content: start;
    opacity: 1;
  }
  .carousel-control-next{
    justify-content: end;
    opacity: 1;
  }
  .arrow{
    height: 60px;
    width: 25px;
    overflow: hidden;
    .prev,
    .next{
      height: 60px;
      width: 60px;
      background-color: $white;
      border-radius: 50%;
      padding: 10px;
      background-position: 10px center;
      background-repeat: no-repeat;
      background-size: 15%;
      // &:hover{
      //   background-color: $off-white;
      // }
    }
    .prev{
      background-image: url(../img/prev.png);
    }
    .next{
      background-image: url(../img/next.png);
    }
  }
  .arrow-prev{
    transform: rotate(180deg)
  }
}

</style>