<template>
  <n-card :title="name">
    <template #cover>
      <img :src="image" alt="">
    </template>
    <slot></slot>
  </n-card>
</template>

<script setup>

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
