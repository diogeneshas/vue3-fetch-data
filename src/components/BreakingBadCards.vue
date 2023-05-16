<template>
  <div>
    <h1>Breaking Bard Cards</h1>
    <p>{{ characters }}</p>
    <div>
      <button @click="page = page + 1">Next</button>
      <button>Back</button>
    </div>
  </div>
</template>

<script setup>
import { ref, watch } from "vue"
import axios from "axios"

const characters = ref(null)
const page = ref(0)

const response =  await axios.get("https://bobsburgers-api.herokuapp.com/characters?limit=8")
characters.value = response.data

watch(page, async () => {
  const res =  await axios.get(`https://bobsburgers-api.herokuapp.com/characters/?limit=8&skip=${page.value * 8}`)
  characters.value = res.data
},
  { immediate: true }
)
</script>
