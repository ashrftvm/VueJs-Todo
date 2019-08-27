<template>
  <header class="title">
    <h1>TodoList</h1>
    <div id="nav">
      <router-link to="/">Home</router-link>&nbsp;|
      <router-link to="/about">About</router-link>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header"
};
</script>

<style scoped>
.title {
  background: #444;
  color: #ccc;
  padding: 30px;
}
#nav a {
  color: #ccc;
  text-decoration: none;
}
</style>