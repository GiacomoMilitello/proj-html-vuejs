<script>
import Top from "./components/header/Top.vue";
import Specials from "./components/main/Specials.vue";
import Jumbo from "./components/main/Jumbo.vue";
import TeamClients from "./components/main/TeamClients.vue";
import Menu from "./components/main/Menu.vue";
import PizzaDeals from "./components/main/PizzaDeals.vue";
import Book from "./components/footer/Book.vue"

export default {
  components: {
    Top,
    Specials,
    Jumbo,
    TeamClients,
    Menu,
    PizzaDeals,
    Book,
  },
};
</script>

<template>

  <header>
    <Top/>
  </header>

  <main class="d-flex flex-column gap-2">
    <Specials/>
    <Jumbo/>
    <TeamClients/>
    <Menu/>
    <PizzaDeals/>
  </main>

  <footer>
    <Book/>
  </footer>
  
</template>

<style lang="scss">
@use "./styles/general.scss";
</style>
