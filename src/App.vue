<script setup>
import RickMortyCards from "./components/RickMortyCards.vue"
import Hero from "./components/Hero.vue"
import BreakingBadCardsSuspense from "./components/BreakingBadCardsSuspense.vue";

import { ref } from "vue"

const isBreakingBad = ref(true)


</script>

<template>
  <Hero :isBreakingBad="isBreakingBad" @selectShow="isBreakingBad = !isBreakingBad"/>
  <KeepAlive>
    <Component :is="isBreakingBad ? BreakingBadCardsSuspense : RickMortyCards" />
  </KeepAlive>
</template>


<style scoped>
.cards {
  height: 700px;
  background-color: rgb(27, 26, 26);
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
