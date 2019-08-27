<template>
  <div id="app">
    <Header />
    <img alt="Vue logo" src="./assets/logo.png" />
    <AddTodo v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-on:del-item="deleteTodo" />
  </div>
</template>

<script>
import Todos from "./components/Todos";
import Header from "./components/layout/Header";
import AddTodo from "./components/AddTodo";
import axios from "axios";

export default {
  name: "app",
  components: {
    Todos,
    Header,
    AddTodo
  },
  data() {
    return {
      todos: []
    };
  },
  methods: {
    deleteTodo(todo) {
      axios
        .delete(`https://jsonplaceholder.typicode.com/todos/${todo.id}`)
        .then(
          res => (this.todos = this.todos.filter(todoL => todoL.id !== todo.id))
        )
        .catch(err => console.log(err));
    },
    addTodo(newVal) {
      axios
        .post("https://jsonplaceholder.typicode.com/todos", newVal)
        .then(res => this.todos.push(res.data))
        .catch(err => console.log(err));
    }
  },
  created() {
    axios
      .get("https://jsonplaceholder.typicode.com/todos?_limit=10")
      .then(res => (this.todos = res.data))
      .catch(err => console.log(err));
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
}
#app img {
  padding: 10px 0 10px 0;
}
input[type="submit"] {
  padding: 12px 20px;
  background: #555;
  color: #fff;
  margin: 8px 0;
  display: inline-block;
  cursor: pointer;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}
input[type="text"] {
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  width: 80%;
}
</style>
