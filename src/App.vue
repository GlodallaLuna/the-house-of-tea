<script setup>
import { RouterView } from 'vue-router'
import {ref, onBeforeMount} from 'vue'

const stock = ref([])

  // Gets all the data from the json file when the page loads
  // 'onBeforeMount' runs before anything is mounted
onBeforeMount(async () => {
    const response = await fetch('/src/assets/stock/stock.json')
    const data = await response.json()
    stock.value = data.stock
}) 
    

</script>

<template>

  <body>
    <RouterView :stock="stock"/>
  </body>
</template>

<style>

</style>
