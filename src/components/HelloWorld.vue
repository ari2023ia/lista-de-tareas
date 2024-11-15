<template>
  <div class="content">
    <p v-if="todo">Tarea: {{ todo.todo }}</p>
  </div>
</template>

 

<script>
import axios from "axios";

 

export default {
  data() {
    return {
      todo: null,
    };
  },
  created() {
    axios.get("https://dummyjson.com/todos/3")
      .then(response => {
        this.todo = response.data;
      })
      .catch(error => {
        console.error("Error fetching data:", error);
      });
  },
};
</script>

 

<style scoped>
.content {
  text-align: center;
}
</style>
