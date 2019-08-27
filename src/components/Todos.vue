<template>
  <div>
    <div v-bind:key="todo.id" v-for="todo in todos">{{todo.title}}</div>
  </div>
</template>

<script>
export default {
  name: "Todos",
  props: ["todos"]
};
</script>