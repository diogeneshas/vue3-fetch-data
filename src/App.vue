<script setup>
import BreakingBadCards from "./components/BreakingBadCards.vue"
import RickMortyCards from "./components/RickMortyCards.vue"
</script>

<template>
  <h1>Hero</h1>
  <Suspense>
    <template #default>
      <BreakingBadCards />
    </template>
    <template #fallback>
      <div>
        <p>Loading...</p>
      </div>
    </template>
  </Suspense>
  <RickMortyCards />
</template>


<style scoped>
</style>
