<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <Todos v-bind:todos="todos" v-on:del-item="deleteTodo" />
  </div>
</template>

<script>
import Todos from "./components/Todos";
export default {
  name: "app",
  components: {
    Todos
  },
  data() {
    return {
      todos: [
        {
          title: "Todo 1",
          completed: false,
          id: 0
        },
        {
          title: "Todo 2",
          completed: true,
          id: 1
        },
        {
          title: "Todo Next",
          completed: false,
          id: 2
        }
      ]
    };
  },
  methods: {
    deleteTodo(todo) {
      this.todos = this.todos.filter(todoL => todoL.id !== todo.id);
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
