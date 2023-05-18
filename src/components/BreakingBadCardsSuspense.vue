<template>
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
</template>

<script setup>
import BreakingBadCards from "./BreakingBadCards.vue"
</script>
