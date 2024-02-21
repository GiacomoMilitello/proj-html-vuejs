<script>
import Top from "./components/header/Top.vue";
import Specials from "./components/main/Specials.vue";
import Jumbo from "./components/main/Jumbo.vue";
import TeamClients from "./components/main/TeamClients.vue";
import Menu from "./components/main/Menu.vue";
import PizzaDeals from "./components/main/PizzaDeals.vue";
import Book from "./components/footer/Book.vue";
import AboutUs from "./components/footer/AboutUs.vue";

export default {
  components: {
    Top,
    Specials,
    Jumbo,
    TeamClients,
    Menu,
    PizzaDeals,
    Book,
    AboutUs,
  },
};
</script>

<template>

  <header class="d-flex flex-column gap-2">
    <Top/>
  </header>

  <main class="d-flex flex-column gap-2">
    <Specials/>
    <Jumbo/>
    <TeamClients/>
    <Menu/>
    <PizzaDeals/>
  </main>

  <footer class="d-flex flex-column gap-2">
    <Book/>
    <AboutUs/>
  </footer>

  <a id="up" class="d-flex align-items-center justify-content-center" href="">
    <img src="./svg/svg-4.svg" alt="">
  </a>
  
</template>

<style lang="scss">
@use "./styles/general.scss";

</style>
