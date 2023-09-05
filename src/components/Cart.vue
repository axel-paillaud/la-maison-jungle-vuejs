<script setup>
import { ref, computed } from 'vue';

const props = defineProps({
  cartIsOpen: Boolean,
  cartList: Object,
});

const computedPlantList = computed(() => {
  let plantList = [];
  props.cartList.forEach((plant) => {
    let isAlreadyHere = plantList.find((element) => element.name === plant.plantName);
    if (isAlreadyHere) {
      const updatedPlant = { ...isAlreadyHere }; // Crée une copie de l'objet trouvé
      updatedPlant.quantity++;
      updatedPlant.price += plant.price;
      // Remplace l'objet original par la copie mise à jour
      plantList = plantList.map((element) =>
        element.name === updatedPlant.name ? updatedPlant : element
      );
    } else {
      plantList.push({
        name: plant.plantName,
        price: plant.price,
        quantity: 1,
      })
    }
  })
  return plantList;
});

const total = computed(() => {
  let total = 0;
  props.cartList.forEach((plant) => {
    total += plant.price;
  });
  return total;
})

</script>

<template>
  <aside v-if="cartIsOpen" class="cart">
    <p v-for="plant in computedPlantList" class="cart-item">
      {{ plant.quantity }} x {{ plant.name }}<span>{{ plant.price }} €</span>
    </p>
    <p class="cart-item cart-total">total<b>{{ total }} €</b></p>
  </aside>
</template>

<style scoped>
  .cart {
    position: absolute;
    background-color: khaki;
    padding: 64px;
    height: calc(100% - 64px);
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  .cart-item {
    display: flex;
    justify-content: space-between;
    gap: 32px;
  }

  .cart-total {
    margin-top: 64px;
  }
  
  b {
    font-weight: bold;
  }
</style>
