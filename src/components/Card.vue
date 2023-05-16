<template>
  <n-card :title="name">
    <template #cover>
      <img :src="image" alt="">
    </template>
    <h4>{{ occupation }}</h4>
  </n-card>
</template>

<script setup>
import { defineProps } from "vue"

const { image, name, occupation } = defineProps([
  'image', 'name', 'occupation'
])
</script>

<style>
/* Card Styles */

.n-card {
  width: 200px;
  margin:10px 20px;

}
.n-card img {
  height: 250px
}

p {
  font-size: 10px;
}

.jobs {
  display: flex;
  flex-wrap: wrap;
}
</style>
