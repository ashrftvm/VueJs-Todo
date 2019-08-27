<template>
  <div>
    <p v-bind:class="{'is-complete':todo.completed}">{{todo.title}}</p>
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
</style>