<script setup>
  import { ref } from 'vue';
  import { cartList } from '@/components/LaMaisonJungle.vue'
  import Plant from '@/components/Plant.vue';
  import Filter from '@/components/Filter.vue';

  let plantList = ref(null);
  let filteredPlantList = ref(null);

  fetch('https://my-json-server.typicode.com/axel-paillaud/la-maison-jungle-vuejs/plants')
  .then((response) => {
    return response.json()
    .then(data => {
      plantList.value = data;
      filteredPlantList.value = plantList.value;
    })
  })
  .catch((error) => {
    console.log(error);
  })

  const addPlant = function(props) {
    cartList.value.push({
      plantName: props.plantName,
      price: props.price,
      id: props.id
    })
  }

  const filter = (filterValue) => {
    if (filterValue === 'all') {
      filteredPlantList.value = plantList.value;
      return;
    }
    let filteredList = plantList.value.filter((plant) => plant.category === filterValue);
    filteredPlantList.value = filteredList;
  }
</script>

<template >
  <main class="main">
    <Filter @filter="filter"/>
    <div v-if="plantList" class="product-container">
      <template v-for="plant in filteredPlantList" :key="plant.id">
        <Plant @add-plant="addPlant"
          :imageUrl="plant.imageUrl"
          :plantName="plant.name"
          :waters="plant.water"
          :suns="plant.sun"
          :price="plant.price"
          :id="plant.id"
        />
    </template>
    </div>

  </main>
</template>

<style scoped>
  .main {
    display: flex;
    justify-content: center;
    padding: 64px;
    flex-direction: column;
  }

  .product-container {
    margin-top: 64px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 24px;
  }

  .filter-container {
    display: flex;
    justify-content: center;
    gap: 32px;
    align-items: center;
    padding: 64px 0 0 0;
  }

  .filter-button {
    padding: 16px 24px;
    border: none;
    border-radius: 16px;
  }
</style>
