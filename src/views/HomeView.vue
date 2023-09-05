<script setup>
  import { ref } from 'vue';
  import { cartList } from '@/components/LaMaisonJungle.vue'
  import Plant from '@/components/Plant.vue';

  let plantList = ref(null);

  fetch('https://my-json-server.typicode.com/axel-paillaud/la-maison-jungle-vuejs/plants')
  .then((response) => {
    return response.json()
    .then(data => {
      plantList.value = data;
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

</script>

<template >
  <main class="main">
    <div v-if="plantList" class="product-container">
      <template v-for="plant in plantList" :key="plant.id">
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
  }

  .product-container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 24px;
  }
</style>
