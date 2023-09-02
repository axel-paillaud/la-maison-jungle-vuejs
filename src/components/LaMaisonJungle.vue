<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  }
})
</script>

<template>
  <header class="header">
    <h1 class="title">La maison jungle</h1>
  </header>
</template>

<style scoped>
  .title {
    color: white;
    font-weight: bold;
  }
  .header {
    background-color: green;
    width: 100%;
    padding: 8px 16px;
    display: flex;
    justify-content: center;
  }
</style>
