<script setup>
  import Item from '@/components/Item.vue';
</script>

<template>
  <main>
    <div class="product-container">
      <Item />
    </div>
    <i class="fa-solid fa-basket-shopping"></i>
  </main>
</template>

<style scoped>
  .product-container {
    display: flex;
    justify-content: center;
  }
</style>
