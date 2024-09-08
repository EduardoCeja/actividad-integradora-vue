<template>
  <div class="about">
    <div class="about-content">
      <!-- Información sobre el proyecto y los responsables -->
      <div>
        <h3>Optativa: Tópicos selectos de entornos de desarrollo: Frameworks</h3>
        <h3>Actividad integradora 1. CRUD en Vue.js</h3>
        <h4>Asesora: Marisol Flores Guerrero</h4>
        <h4>Alumno: Eduardo Ceja Robles</h4>

        <!-- Formulario para crear/actualizar elementos -->
        <form @submit.prevent="isEditing ? updateItem() : addItem()">
          <input v-model="formData.name" placeholder="Nombre del elemento" required />
          <button type="submit">{{ isEditing ? 'Actualizar' : 'Agregar' }}</button>
          <button type="button" v-if="isEditing" @click="cancelEdit()">Cancelar</button>
        </form>

        <!-- Lista de elementos -->
        <ul>
          <li v-for="(item, index) in items" :key="index">
            {{ item.name }}
            <button @click="editItem(index)">Editar</button>
            <button @click="deleteItem(index)">Eliminar</button>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: 'AboutPage',
  data() {
    return {
      items: [], // Arreglo que contiene los elementos del CRUD
      formData: { name: '' }, // Información del formulario
      isEditing: false, // Indicador para saber si estamos editando
      currentIndex: null, // Índice del elemento que estamos editando
    };
  },
  methods: {
    // Agregar un nuevo elemento
    addItem() {
      this.items.push({ ...this.formData });
      this.resetForm(); // Reinicia el formulario después de agregar
    },
    // Editar un elemento existente
    editItem(index) {
      this.formData = { ...this.items[index] }; // Llena el formulario con los datos del elemento seleccionado
      this.isEditing = true;
      this.currentIndex = index; // Guarda el índice del elemento en edición
    },
    // Actualizar el elemento
    updateItem() {
      this.items[this.currentIndex] = { ...this.formData }; // Actualiza el elemento en la lista
      this.resetForm(); // Reinicia el formulario después de actualizar
    },
    // Eliminar un elemento
    deleteItem(index) {
      this.items.splice(index, 1); // Elimina el elemento de la lista
    },
    // Cancelar la edición
    cancelEdit() {
      this.resetForm(); // Reinicia el formulario sin hacer cambios
    },
    // Reiniciar el formulario
    resetForm() {
      this.formData = { name: '' }; // Vacía el campo del formulario
      this.isEditing = false; // Cambia el estado a modo de creación
      this.currentIndex = null;
    },
  },
};

</script>

<style scoped>
.about {
  display: flex;
  flex-direction: column; /* Elementos alineados en columna */
  justify-content: center; /* Centrado vertical */
  align-items: center; /* Centrado horizontal */
  height: 100vh;
  background: linear-gradient(90deg, rgba(2, 0, 36, 0.67) 11%, rgba(121, 9, 9, 0.55) 57%, rgba(255, 0, 0, 0.49) 100%);
  background-size: cover;
  background-position: center;
  text-align: center; /* Texto centrado */
}

.about-content {
  background-color: rgba(255, 255, 255, 0.85); /* Fondo semi-transparente */
  padding: 40px;
  border-radius: 15px;
  box-shadow: 0 10px 14px rgba(0, 0, 0, 0.9);
  text-align: center;
  max-width: 600px; /* Ancho máximo del contenedor */
}

form {
  margin-bottom: 20px;
}

ul {
  list-style: none; /* Quita los puntos de la lista */
  padding: 0;
}

li {
  margin: 5px 0; /* Margen entre elementos de la lista */
}

button {
  margin-left: 10px; /* Espacio entre botones */
}
</style>
