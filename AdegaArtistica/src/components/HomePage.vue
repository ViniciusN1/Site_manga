
<template>
  <div class="login-container">
    <div class="login-box" v-if="!BottomRegis">
      <h2>Login</h2>
      <input type="email" placeholder="E-mail" v-model="email" />
      <div class="password-field">
        <input :type="showPassword ? 'text' : 'password'" placeholder="Senha" v-model="password" />
        <span class="toggle" @click="showPassword = !showPassword">veja👁</span>
      </div>
      <button @click="login">Entrar</button>
      <a href="#" class="forgot-password">Esqueceu sua senha?</a>
      <a href="#" class="creatNewPerson" @click.prevent="RegistrarOn">criar nova conta</a>
    </div>

    <!-- Tela de Cadastro -->
    <div class="login-box" v-else>
      <h2>Cadastrar</h2>
      <input type="text" placeholder="Nome" v-model="nome" />
      <input type="email" placeholder="E-mail" v-model="email" />
      <input type="password" placeholder="Senha" v-model="password" />
      <button @click="cadastrar">Cadastrar</button>
      <a href="#" class="creatNewPerson" @click.prevent="VoltarLogin">Voltar ao login</a>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

const email = ref("");
const password = ref("");
const showPassword = ref(false);
const nome = ref("");
const BottomRegis = ref(false);

function login() {
  alert(`E-mail: ${email.value}, Senha: ${password.value}`);
}

function RegistrarOn() {
  BottomRegis.value = true;
}

function VoltarLogin() {
  BottomRegis.value = false;
}

function cadastrar() {
  alert(`Nome: ${nome.value}, E-mail: ${email.value}, Senha: ${password.value}`);
  // Aqui você poderia enviar para a API ou salvar localStorage
  VoltarLogin(); // Volta para login após cadastro
}
</script>

<style scoped>
.login-container {
  background: url("https://images.unsplash.com/photo-1506748686214-e9df14d4d9d0") no-repeat center center / cover;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

.login-box {
  background: rgba(255, 255, 255, 0.15);
  backdrop-filter: blur(15px);
  padding: 2rem;
  border-radius: 15px;
  width: 300px;
  text-align: center;
  box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
}

.login-box h2 {
  margin-bottom: 1.5rem;
  color: white;
}

.login-box input {
  width: 100%;
  padding: 10px;
  margin: 8px 0;
  border: none;
  border-radius: 8px;
  outline: none;
}

.password-field {
  position: relative;
}

.password-field .toggle {
  position: absolute;
  right: 10px;
  top: 8px;
  cursor: pointer;
  color: aqua;
}

.login-box button {
  width: 100%;
  padding: 10px;
  border: none;
  border-radius: 8px;
  background: linear-gradient(to right, #00b4db, #0083b0);
  color: white;
  font-weight: bold;
  cursor: pointer;
  margin-top: 10px;
}

.forgot-password {
  display: block;
  margin-top: 10px;
  color: white;
  font-size: 0.9rem;
  text-decoration: none;
}

</style>
