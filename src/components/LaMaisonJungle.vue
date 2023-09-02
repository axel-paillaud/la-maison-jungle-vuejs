<script setup>
  import HomeView from '@/views/HomeView.vue';
  import {RouterLink, RouterView} from 'vue-router';
</script>

<template>
  <header class="header">
    <button class="cart-button"><i class="fa-solid fa-basket-shopping"></i>Cart</button>
    <h1 class="title">La maison jungle</h1>
    <nav class="nav-menu">
      <RouterLink to="/">Shop</RouterLink>
      <RouterLink to="/about">About</RouterLink>
    </nav>
  </header>
  <RouterView />

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
    justify-content: space-between;
    align-items: center;
  }

  .nav-menu {
    display: flex;
    gap: 16px;
    justify-self: end;
  }

  .nav-menu a {
    color: white;
    text-decoration: none;
  }

  .cart-button {
    display: flex;
    gap: 8px;
    align-items: center;
    padding: 8px 16px;
  }
</style>
