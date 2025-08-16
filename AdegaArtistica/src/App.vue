<script setup lang="ts">
import { RouterView } from 'vue-router'
</script>

<template>

  <RouterView />
</template>
<style>
html, body, #app {
  margin: 0;
  padding: 0;
  height: 100%;
  width: 100%;
}

body {
  background: url('/caminho/da-sua-imagem.jpg') no-repeat center center fixed;
  background-size: cover;
}
</style>
