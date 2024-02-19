<script>
export default {
  name: "NavBar",
  props: [
    'navLinks',
    'buyLinks'
  ],
  data() {
        return {
            revImages: [
                {
                  back: 'src/img/h3-rev-img-1.png',
                  img: 'src/img/h3-rev-img-2.png'
                },
                {
                  back: 'src/img/h3-rev-img-3.png',
                  img: 'src/img/h3-rev-img-4.png'
                },
                {
                  back: 'src/img/h3-rev-img-5.png',
                  img: 'src/img/h3-rev-img-6.png'
                },
            ]
        };
    }
};
</script>

<template>
  <div id="nav-bar">
    <ul class="w-75 mx-auto d-flex justify-content-between align-items-center py-4">
        <li class="btn-orange text-uppercase">order online</li>
        <li>
            <li class="d-flex align-items-center gap-4">
              <a v-for="(link, index) in navLinks" :key="index" href="#" class="text-uppercase d-flex align-items-center gap-1">   
                <img v-if="link.img" :src="link.img" alt="icon" />
                {{ link.link }}
              </a>
            </li>
        </li>
        <li>
            <li class="d-flex align-items-center gap-4">
              <a v-for="(link, index) in buyLinks" :key="index" href="#" class="text-uppercase d-flex align-items-center gap-1">
                <img v-if="link.img" :src="link.img" alt="icon" />
                {{ link.link }}
              </a>
            </li>
        </li>
    </ul>

    <div id="carouselExampleRide" class="carousel slide carousel-fade" data-bs-ride="true">
  <div class="carousel-inner">
    <div class="carousel-item" v-for="(image, index) in revImages" :key="index" :class="{ active: index === 0 }">
      <div id="back" :style="{ backgroundImage: 'url(' + image.back + ')' }">
        <figure class="w-25 mx-auto">
        <img :src="image.img" class="d-block w-100 img-fluid" alt="Image">
      </figure>
      </div>
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
  min-height: 550px;
  background-color: $dark-gray;
  background-image: url(../../img/cielostellato.PNG);
  @include bg-cover;
  color: $white;
  a{
    height: 105px;
    color: $white;
    border-bottom: 3px solid transparent;
    &:hover{
      color: $orange;
      border-bottom: 3px solid $orange;
    }
  }
  ul img{
    max-width: 140px;
  };
  #carouselExampleRide{
    #back{
      @include bg-contain;
    }
    img{
      max-width: 280px
    };
  }
  
}
</style>