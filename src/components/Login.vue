<template>
  <div>
    <h1>Iniciar sesión</h1>
    <form @submit.prevent="login">
      <label for="username">Usuario:</label>
      <input type="text" id="username" v-model="username" required>
      <label for="password">Contraseña:</label>
      <input type="password" id="password" v-model="password" required>
      <div class="button-group">
        <button type="submit">Iniciar sesión</button>
        <router-link to="/" class="router-link-button">
          <button type="button" class="register-button">Pagina Principal</button>
        </router-link>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data() {
    return {
      username: '',
      password: ''
    }
  },
  methods: {
    login() {
      // Simulación de inicio de sesión
      if (this.username === 'usuario' && this.password === 'contraseña') {
        alert('Inicio de sesión exitoso');
        // Aquí puedes redirigir a la página de inicio
        this.$router.push('/');
      } else {
        alert('Credenciales incorrectas');
      }
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
