<script setup lang="ts">
import TheWelcome from '../components/HomePage.vue'
import BottomNav from '../components/BottomNav.vue'


</script>

<template>
  <main>
    <TheWelcome />
    <BottomNav />
  </main>
</template>

<style>
.login-container {
  background: url("https://images.unsplash.com/photo-1506748686214-e9df14d4d9d0") no-repeat center center;
  background-size: cover; /* Faz a imagem preencher toda a tela */
  height: 100vh;
  width: 100vw; /* Ocupa toda a largura */
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
