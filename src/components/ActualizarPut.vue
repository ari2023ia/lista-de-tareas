<template>
    <div class="content">
      <button @click="updateTodo">Actualizar Tarea</button>
    </div>
  </template>
  
  <script>
  import axios from "axios";
  
  export default {
    methods: {
      updateTodo() {
        const updatedTodo = {
          title: "Tarea actualizada",
          completed: true
        };
  
        axios.put("https://dummyjson.com/todos/1", updatedTodo)
          .then(response => {
            console.log("Tarea actualizada:", response.data);
          })
          .catch(error => {
            console.error("Error updating todo:", error);
          });
      }
    }
  };
  </script>
  
  <style scoped>
  .content {
    text-align: center;
  }
  </style>