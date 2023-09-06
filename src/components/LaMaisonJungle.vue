<script setup>
import {RouterLink, RouterView} from 'vue-router';
import { ref, reactive } from 'vue';
import Cart from '@/components/Cart.vue';

const cartIsOpen = ref(false);

function toggleCart() {
  cartIsOpen.value = !cartIsOpen.value;
}

</script>

<script>
let lists = [];
export const cartList = ref(lists);
</script>

<template>
  <header class="header">
    <button class="cart-button" @click="toggleCart"><i class="fa-solid fa-basket-shopping"></i>Cart</button>
    <h1 class="title">La maison jungle</h1>
    <nav class="nav-menu">
      <RouterLink to="/">Shop</RouterLink>
      <RouterLink to="/about">About</RouterLink>
    </nav>
  </header>
  <Cart :cartList="cartList" :cartIsOpen="cartIsOpen"/>
  <RouterView />

</template>

<style scoped>
  .title {
    color: white;
    font-weight: bold;
  }
  .header {
    position: fixed;
    z-index: 20;
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
