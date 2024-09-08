<!-- src/App.vue -->
<template>
  <div id="app">
    <nav>
      <router-link to="/" class="nav-link" active-class="active">Home</router-link>
      <router-link to="/about" class="nav-link" active-class="active">Actividad integradora 1. CRUD en Vue.js</router-link>
    </nav>
    <router-view />
  </div>
</template>

<script>
export default {
  name: 'App',
};
</script>

<style>
nav {
  display: flex;
  gap: 15px;
  padding: 20px;
  background-color: #f8f9fa;
  border-bottom: 2px solid #ddd;
}

/* Estilos para los enlaces de navegación */
.nav-link {
  text-decoration: none; /* Elimina el subrayado */
  color: #333; /* Color de texto */
  font-size: 18px; /* Tamaño de fuente */
  padding: 10px 15px; /* Espaciado interno */
  border-radius: 5px; /* Bordes redondeados */
  transition: background-color 0.3s, color 0.3s; /* Transiciones suaves para el hover */
}

/* Efecto hover para los enlaces */
.nav-link:hover {
  background-color: #007bff; /* Color de fondo al pasar el cursor */
  color: white; /* Color de texto al pasar el cursor */
}

/* Estilo para el enlace activo */
.active {
  font-weight: bold; /* Negrita para el enlace activo */
  color: #007bff; /* Color de texto para el enlace activo */
}
</style>
    