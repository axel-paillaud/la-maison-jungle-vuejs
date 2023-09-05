<script setup>

  const props = defineProps({
    imageUrl: String,
    plantName: String,
    waters: Number,
    suns: Number,
    price: Number,
    id: String,
  })

</script>

<template>
    <div class="plant-container">
      <div class="plant-image-description">
        <div class="plant-image">
          <img 
            :src="imageUrl"
            alt="ficus lyrata"
            width="256"
            height="256"
          >
        </div>
        <div class="plant-description">
          <h3 class="plant-name">{{ plantName }}</h3>

          <!-- Water icons -->
          <div class="water-icons">
            <i v-for="(water, index) in waters" :key="index" class="fa-solid fa-droplet"></i>
          </div>

          <!-- Light icons -->
          <div class="sun-icons">
            <i v-for="(sun, index) in suns" :key="index" class="fa-solid fa-sun"></i>
          </div>

          <!-- Price and Add to Cart button -->
          <strong class="price">{{ price }} €</strong>
          <button class="cart-button" @click="$emit('addPlant', props)">Add to Cart<i class="fa-solid fa-basket-shopping"></i></button>
        </div>
      </div>
    </div>
</template>

<style scoped>
.plant-container {
  border-radius: 16px;
  border: 1px solid rgb(192, 192, 192);
  overflow: hidden;
  box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);;
}
.plant-name {
  font-size: 16px;
  font-weight: bold;
  text-transform: capitalize;
}
.plant-image-description {
  display: flex;
  gap: 64px;
}

.plant-description {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  padding: 0 16px;
}

.plant-image {
  height: 256px;
  width: 256px;
}
.water-icons {
  display: flex;
  gap: 8px;
  color: rgb(10, 10, 85);
}

.sun-icons {
  display: flex;
  gap: 8px;
  color: rgb(179, 128, 20);
}

.price {
  font-size: 24px;
}
.cart-button {
  display: flex;
  gap: 8px;
  padding: 8px 16px;
  align-items: center;
  cursor: pointer;
}
</style>
