<script>
import Carousel from "../Carousel.vue";

export default {
  name: "NavBar",
  components: {
    Carousel,
},
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

<!-- -- LINKS NAV-BAR -- -->
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

<!-- -- CAROUSEL NAV-BAR -- -->
<Carousel :images="revImages" :backgrounds="revImages" />
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
}
</style>