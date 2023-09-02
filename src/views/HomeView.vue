<script setup>
  import Item from '@/components/Item.vue';
  import Cart from '@/components/Cart.vue';
</script>

<template>
  <main>
    <cart :show="true"/>
    <div class="product-container">
      <item />
    </div>
    <i class="fa-solid fa-basket-shopping"></i>
    <i class="fa-solid fa-droplet"></i>
    <i class="fa-solid fa-sun"></i>

  </main>
</template>

<style scoped>
  .product-container {
    display: flex;
    justify-content: center;
  }
</style>
