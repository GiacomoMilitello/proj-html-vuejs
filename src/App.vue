<script>
import Top from "./components/header/Top.vue";
import Specials from "./components/main/Specials.vue"
import Jumbo from "./components/main/Jumbo.vue"
import TeamClients from "./components/main/TeamClients.vue"

export default {
  components: {
    Top,
    Specials,
    Jumbo,
    TeamClients,
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
  </main>
  
</template>

<style lang="scss">
@use "./styles/general.scss";
</style>
