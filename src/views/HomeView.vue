<script setup>
  import Plant from '@/components/Plant.vue';
</script>

<template>
  <main>
    <div class="product-container">
      <Plant />
    </div>

  </main>
</template>

<style scoped>
  .product-container {
    display: flex;
    justify-content: center;
    padding: 64px;
  }
</style>
