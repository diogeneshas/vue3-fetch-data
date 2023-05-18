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
      <div class="cards spinner">
        <n-spin size="large"></n-spin>
      </div>
    </template>
  </Suspense>
  <RickMortyCards />
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
