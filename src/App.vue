<script>
import Top from "./components/header/Top.vue";
import Specials from "./components/main/Specials.vue"

export default {
  components: {
    Top,
    Specials,
  },
};
</script>

<template>

  <header>
    <Top/>
  </header>

  <main>
    <Specials/>
  </main>
  
</template>

<style lang="scss">
@use "./styles/general.scss";
</style>
