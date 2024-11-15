<template>
  <hello-world />
  <peticion-axios />
  <actualizar-put />
  <delete-tarea />
  <div id="app">
    <todo-list />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import TodoList from './components/TodoList.vue';
import PeticionAxios from './components/PeticionAxios.vue';
import ActualizarPut from './components/ActualizarPut.vue';
import DeleteTarea from './components/DeleteTarea.vue';
import todoService from './service/todoService';

export default {
  name: 'App',
  components: {
    TodoList,
    HelloWorld,
    PeticionAxios,
    ActualizarPut,
    DeleteTarea
  },
  data() {
    return {
      todos: []
    };
  },
  async created() {
    try {
      const response = await todoService.getTodos();
      this.todos = response.data;
      console.log("service:", JSON.stringify(this.todos));
    } catch (error) {
      console.error("Error fetching todos:", error);
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align: center;
  margin-top: 60px;
}
</style>


