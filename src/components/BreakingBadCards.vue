<template>
  <div class="container">
    <div class="cards">
      <Card v-for="character in characters" :key="character.id" :image="character.image" :name="character.name" :occupation="character.occupation"/>
    </div>
  </div>
</template>

<script setup>
import Card from "@/components/Card.vue"
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

<style scoped>

/* Breaking Bad Styles */

.container {
  background-color: rgb(27, 26, 26);
  padding: 30px
}
.cards {
  max-width: 1000px;
  margin: 0 auto;
  display: flex;
  flex-wrap: wrap;
  height: 900px
}
.cards h3 {
  font-weight: bold;
}
.cards p {
  font-size: 10px;
}
.jobs {
  display: flex;
  flex-wrap: wrap;
}
.button-container {
  display: flex;
  justify-content: center;
  padding-top: 30px
}
.button-container button {
  border: none;
  width: 50px;
  height: 50px;
  border-radius: 100%;
  margin: 0 5px;
  cursor: pointer;
}
.spinner {
  display: flex;
  align-items: center;
  justify-content: center;
}

</style>
