<script setup>
import BreakingBadCards from "./components/BreakingBadCards.vue"
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
</template>

<style scoped>
</style>
