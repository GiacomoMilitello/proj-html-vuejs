<script>
import NavBar from "./NavBar.vue";

export default {
  name: "Top",
  components: {
    NavBar,
  },
  data() {
    return {
      navLinks: [
        {
          link : 'home',
          svg : 'src/svg/svg-0.svg',
        },
        {
          link : 'pages',
        },
        {
          link : 'menu',
        },
        {
          img : 'src/img/h5-logo-divided-header'
        },
        {
          link : 'event',
        },
        {
          link : 'blog',
        },
        {
          link : 'landing',
        },
      ],
      buyLinks: [
        {
          link : 'cart',
          svg : 'src/svg/svg-1.svg',
        },
        {
          link : 'search',
          svg : 'src/svg/svg-2.svg',
        },
      ],
    }
  }
};
</script>

<template>
  <NavBar/>
</template>

<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;

// h1 {
//   color: $font-color-second;
//   @include main-font-start;
// }
</style>