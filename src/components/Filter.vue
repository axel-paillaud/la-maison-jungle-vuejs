<script setup>
</script>

<template >
  <div class="filter-container">
    <button @click="$emit('filter', 'all')" class="filter-button">Toutes</button>
    <button @click="$emit('filter', 'classique')" class="filter-button">classique</button>
    <button @click="$emit('filter', 'extérieur')" class="filter-button">extérieur</button>
    <button @click="$emit('filter', 'plante grasse')" class="filter-button">plante Grasse</button>
  </div>
</template>

<style scoped>
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
    text-transform: capitalize;
  }
</style>
