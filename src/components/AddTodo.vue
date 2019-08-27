<template>
  <div class="container">
    <form>
      <input type="text" name="title" placeholder="Enter Todo Title" />
      <input type="submit" value="Submit" />
    </form>
  </div>
</template>

<script>
export default {
  name: "AddTodo"
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

form input[type="text"] {
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  width: 80%;
}

form input[type="submit"] {
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
</style>