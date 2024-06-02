<template>
  <div>
    <h1>Registro</h1>
    <form @submit.prevent="register">
      <label for="username">Usuario:</label>
      <input type="text" id="username" v-model="username" required>
      <label for="password">Contraseña:</label>
      <input type="password" id="password" v-model="password" required>
      <label for="email">Correo Electrónico:</label>
      <input type="email" id="email" v-model="email" required>
      <div class="button-group">
        <button type="submit">Registrarse</button>
        <router-link to="/" class="router-link-button">
          <button type="button" class="register-button">Pagina Principal</button>
        </router-link>
      </div>
    </form>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'Register',
  data() {
    return {
      username: '',
      password: '',
      email: ''
    }
  },
  methods: {
    register() {
      axios.post('http://localhost:5000/api/users/register', {
        username: this.username,
        password: this.password,
        email: this.email
      })
      .then(response => {
        alert(response.data);
      })
      .catch(error => {
        console.error(error);
        alert('Error al registrar el usuario');
      });
    }
  }
}
</script>

<style scoped>
/* Asegúrate de que los campos de entrada estén uno debajo del otro y centrados */
form {
  display: flex;
  flex-direction: column;
  align-items: center; /* Centro horizontal */
  width: 100%;
}

/* Centrar el contenedor del formulario */
form > div, form > label, form > input {
  width: 100%;
  max-width: 300px; /* Ajusta según sea necesario */
}

/* Agrupamos los botones para que estén uno al lado del otro */
.button-group {
  display: flex;
  justify-content: center; /* Centro horizontal */
  gap: 10px; /* Espacio entre los botones */
  width: 100%;
  margin-top: 15px;
}

.button-group button, 
.button-group .router-link-button button {
  margin: 0;
}

.router-link-button {
  display: inline-block;
}
</style>
