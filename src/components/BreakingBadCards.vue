<template>
  <div>
    <h1>Breaking Bard Cards</h1>
  </div>
</template>

<script setup>
import axios from "axios"

const response =  await axios.get("https://thronesapi.com/api/v2/Characters")


</script>
