<!-- src/views/Home.vue -->
<template>
  <div class="home">

    <!-- Contenido de la página de inicio -->
    <div class="home-content">
      <!-- Título y mensaje de bienvenida existentes -->
      <h1>Home</h1>
      <h4>Bienvenido a la página de inicio</h4>
      <h3>Optativa: Tópicos selectos de entornos de desarrollo: Frameworks</h3>
      <h3>Actividad 1.3. Prototipado en Vue.js</h3>
      <h4>Asesora: Marisol Flores Guerrero</h4>
      <h4>Alumno: Eduardo Ceja Robles</h4>
      <!-- Lista de ítems -->
      <!--<ItemList :items="items" />-->
    </div>
  </div>
</template>
<script>
export default {
  name: 'HomePage', // Mantener nombre actualizado
};
</script>

<style scoped>
.home {
  display: flex;
  flex-direction: column; /* Cambia a columna para que el contenido se apile verticalmente */
  justify-content: center; /* Centra verticalmente los elementos */
  align-items: center; /* Centra horizontalmente los elementos */
  height: 100vh;
  background: linear-gradient(90deg, rgba(2, 0, 36, 0.67) 11%, rgba(121, 9, 9, 0.55) 57%, rgba(255, 0, 0, 0.49) 100%);
  text-align: center; /* Alinea el texto al centro */
}


/* Aseguramos que el contenido esté centrado horizontalmente */
.home-content {
  text-align: center;
  background-color: #ffffff;
  padding: 30px;
  border-radius: 15px;
  box-shadow: 0 10px 14px rgba(0, 0, 0, 0.9);
  max-width: 600px; /* Limitar el ancho máximo para un diseño más centrado */
}

h1, h3, h4, h2 {
  margin-bottom: 10px;
  color: #333;
}

h2 {
  margin-top: 20px;
}

p {
  margin-bottom: 25px;
  color: #555;
}
</style>
