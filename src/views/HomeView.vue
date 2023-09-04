<script setup>
  import { ref } from 'vue';
  import Plant from '@/components/Plant.vue';

  //Does I need a reactive variable here ?
  let plantList = [];

  fetch('https://my-json-server.typicode.com/axel-paillaud/la-maison-jungle-vuejs/plants')
  .then((response) => {
    return response.json()
    .then(data => {
      plantList = data;
      console.log(plantList);
    })
  })
  .catch((error) => {
    console.log(error);
  })
</script>

<template>
  <main class="main">
    <div class="product-container">
      <Plant />
    </div>

  </main>
</template>

<style scoped>
  .main {
    display: flex;
    justify-content: center;
    padding: 64px;
  }
</style>
