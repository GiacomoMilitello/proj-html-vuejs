<script>
import Top from "./components/header/Top.vue";
import Specials from "./components/main/Specials.vue"
import Jumbo from "./components/main/Jumbo.vue"

export default {
  components: {
    Top,
    Specials,
    Jumbo,
  },
};
</script>

<template>

  <header>
    <Top/>
  </header>

  <main>
    <Specials/>
    <Jumbo/>
  </main>
  
</template>

<style lang="scss">
@use "./styles/general.scss";
</style>
