<template>
  <div class="content">
    <button @click="addTodo">Añadir Tarea</button>
  </div>
</template>

<script>
import axios from "axios";

export default {
  methods: {
    async addTodo() {
      const newTodo = {
        todo: "Comprar frutas", // Tarea nueva
        completed: false,       // Estado inicial
        userId: 1               // ID del usuario
      };

      try {
        const response = await axios.post(
          "https://dummyjson.com/todos/add",
          newTodo,
          {
            headers: {
              "Content-Type": "application/json"
            }
          }
        );
        console.log("Tarea añadida:", response.data);
      } catch (error) {
        console.error("Error añadiendo la tarea:", error.response?.data || error.message);
      }
    }
  }
};
</script>

<style scoped>
.content {
  text-align: center;
}
</style>
