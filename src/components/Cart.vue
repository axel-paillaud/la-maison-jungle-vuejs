<script setup>
  defineProps({
    cartIsOpen: Boolean,
  });

</script>

<template>
  <aside v-if="cartIsOpen" class="cart">
    <p class="cart-item">2 x Monstera<span>12 €</span></p>
    <p class="cart-item">1 x Plante grimpante<span>24 €</span></p>
    <p class="cart-item"> 4 x Je sais pas quoi<span>98 €</span></p>
    <p class="cart-item cart-total">total<b>823 €</b></p>
  </aside>
</template>

<style scoped>
  .cart {
    position: absolute;
    background-color: khaki;
    padding: 64px;
    height: 100%;
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
