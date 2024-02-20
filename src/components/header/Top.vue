<script>
import NavBar from "./NavBar.vue";
import HeaderBottom from "./HeaderBottom.vue";

export default {
  name: "Top",
  components: {
    NavBar,
    HeaderBottom,
},
  data() {
    return {
      navLinks: [
        {
          link : 'home',
          img : 'src/svg/svg-0.svg',
        },
        {
          link : 'pages',
        },
        {
          link : 'menu',
        },
        {
          img : 'src/img/h5-logo-divided-header.png'
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
          img : 'src/svg/svg-1.svg',
        },
        {
          link : 'search',
          img : 'src/svg/svg-2.svg',
        },
      ],
    }
  }
};
</script>

<template>
  <NavBar :navLinks="navLinks" :buyLinks="buyLinks"/>
  <HeaderBottom/>
</template>

<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;
</style>