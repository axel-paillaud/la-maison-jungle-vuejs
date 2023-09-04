<script setup>
  defineProps({
    imageUrl: String,
    plantName: String,
    water: Number,
    sun: Number,
    price: Number,
  })
</script>

<template>
    <div class="plant-container">
      <div class="plant-image-description">
        <div class="plant-image">
          <img 
            src="https://webshop.plnts.com/media/catalog/product/cache/aa5d334f459227518b6c3cf7ea9d29ed/p/l/pl.xl.006_-_ficus_lyrata-vierkant.jpg" 
            alt="ficus lyrata"
            width="256"
            height="256"
          >
        </div>
        <div class="plant-description">
          <h3 class="plant-name">ficus lyrata</h3>

          <!-- Water icons -->
          <div class="water-icons">
            <i class="fa-solid fa-droplet"></i>
            <i class="fa-solid fa-droplet"></i>
            <i class="fa-solid fa-droplet"></i>
          </div>

          <!-- Light icons -->
          <div class="sun-icons">
            <i class="fa-solid fa-sun"></i>
            <i class="fa-solid fa-sun"></i>
            <i class="fa-solid fa-sun"></i>
          </div>

          <!-- Price and Add to Cart button -->
          <div class="price-add-cart">
            <strong class="price">28 €</strong>
            <button class="cart-button">Add to Cart<i class="fa-solid fa-basket-shopping"></i></button>
          </div>
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

.price-add-cart {
  display: flex;
  gap: 8px;
  align-items: center;
}

.price {
  font-size: 24px;
}
.cart-button {
  display: flex;
  gap: 8px;
  padding: 16px;
  align-items: center;
  cursor: pointer;
}
</style>
