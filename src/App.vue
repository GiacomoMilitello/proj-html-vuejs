<script>
import Top from "./components/header/Top.vue";
import Specials from "./components/main/Specials.vue";
import Jumbo from "./components/main/Jumbo.vue";
import TeamClients from "./components/main/TeamClients.vue";
import Menu from "./components/main/Menu.vue";
import PizzaDeals from "./components/main/PizzaDeals.vue";
import Bottom from "./components/footer/Bottom.vue";

export default {
  components: {
    Top,
    Specials,
    Jumbo,
    TeamClients,
    Menu,
    PizzaDeals,
    Bottom,
  },
  data() {
    return {
      itemsCount: 0,
    };
  },
  methods: {
    incrementItems() {
      this.itemsCount++;
    },
    scrollToNavBar: function() {
      document.getElementById('up').addEventListener('click', function(event) {
        event.preventDefault();
        document.getElementById('nav-bar').scrollIntoView({behavior: 'smooth'});
      });
    }
  },
  mounted() {
    this.scrollToNavBar();
  }
};
</script>

<template>

  <header class="d-flex flex-column gap-2">
    <Top :itemsCount="itemsCount"/>
  </header>

  <main class="d-flex flex-column gap-2">
    <Specials/>
    <Jumbo/>
    <TeamClients/>
    <Menu :incrementItems="incrementItems"/>
    <PizzaDeals/>
  </main>

  <footer class="d-flex flex-column gap-2">
    <Bottom/>
  </footer>

  <a id="up" class="d-flex align-items-center justify-content-center" href="">
    <img src="./svg/svg-4.svg" alt="">
  </a>
  
</template>

<style lang="scss">
@use "./styles/general.scss";

</style>
