<template>
  <div class="todo-container">
    <div class="todo-item">
      <input type="checkbox" />
      <p v-bind:class="{'is-complete':todo.completed}">{{todo.title}}</p>
      <button class="del">❌</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"]
};
</script>

<style scoped>
.is-complete {
  text-decoration: line-through;
}
.todo-item {
  text-align: center;
  /* border: 1px solid red; */
  display: flex;
  width: 100%;
  align-items: center;
  justify-items: flex-start;
  display: flex;
}

.todo-item p {
  width: 100%;
}

.todo-item input[type="checkbox"] {
  font-size: 50px;
  margin: 5px;
}
.todo-container {
  display: flex;
  flex: 1 1 100%;
  background: #aaa;
  margin-bottom: 10px;
}
.del {
  background: #aaa;
  border: none;
  cursor: pointer;
  float: right;
}
</style>