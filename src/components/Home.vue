<template>
   <div>
      <h1>AZ Marketing</h1>
      <h1>Somos una gran familia</h1>
      <div style="margin-top: 15px;">
        <router-link to="/login">
          <button class="login-button">Iniciar Sesión</button>
        </router-link>
        <router-link to="/register" style="margin-left: 15px;">
          <button class="login-button">Registrar</button>
        </router-link>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Home',
  }
  </script>
  
  <style scoped>
  /* Copia aquí los estilos que necesites de App.vue */
  </style>
  