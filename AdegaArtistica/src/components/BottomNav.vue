<template>
  <div class="bottom-nav">
    <RouterLink to="/projetos" class="nav-item">
      📂 Projetos
    </RouterLink>
    <RouterLink to="/perfil" class="nav-item">
      👤 Perfil
    </RouterLink>
  </div>
</template>

<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<style scoped>
.bottom-nav {
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  background: rgba(255, 255, 255, 0.85);
  display: flex;
  justify-content: space-around;
  padding: 10px 0;
  box-shadow: 0 -2px 5px rgba(0,0,0,0.1);
  backdrop-filter: blur(10px);
}

.nav-item {
  text-decoration: none;
  color: #333;
  font-weight: bold;
  font-size: 1rem;
  display: flex;
  align-items: center;
  gap: 5px;
}

.nav-item:hover {
  color: #b44b00; /* cor no estilo de adega/vinho */
}
</style>
