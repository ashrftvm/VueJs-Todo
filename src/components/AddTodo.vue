<template>
  <div class="container">
    <form @submit="addTodo">
      <input type="text" v-model="title" name="title" placeholder="Enter Todo Title" />
      <input type="submit" value="Submit" />
    </form>
  </div>
</template>

<script>
// import uuid from "uuid";

export default {
  name: "AddTodo",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        title: this.title,
        completed: false
      };
      //send to parent for storing
      this.$emit("add-todo", newTodo);
      this.title = "";
    }
  }
};
</script>

<style scoped>
form {
  display: flex;
  flex: 1 1 100%;
  background: #aaa;
  margin-bottom: 10px;
  padding: 20px 0 20px 0;
  justify-content: space-evenly;
  align-items: center;
  border-radius: 20px 0 20px 0;
}
</style>