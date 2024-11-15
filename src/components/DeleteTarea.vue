<template>
    <div class="content">
      <button @click="deleteTodo">Eliminar Tarea</button>
    </div>
  </template>
  
  <script>
  import axios from "axios";
  
  export default {
    methods: {
      deleteTodo() {
        axios.delete("https://dummyjson.com/todos/1")
          .then(response => {
            console.log("Tarea eliminada:", response.data);
          })
          .catch(error => {
            console.error("Error deleting todo:", error);
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