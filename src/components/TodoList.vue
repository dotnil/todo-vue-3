<template>
  <div class="todo-list">
    <div class="todo-list__wrapper">
      <h1 class="todo-list__header">Todo List</h1>

      <ul class="todo-list__container">
        <li v-for="todo in todos" :key="todo.name" class="todo-list__item">
          {{ todo.name }} <a class="todo-list__delete" href="#">×</a>
        </li>
      </ul>
      <input class="todo-list__new" type="text" />
      <a href="#" class="todo-list__save-new">Save</a>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todos: [{ name: "function" }, { name: "take a rest" }]
    }
  }
}
</script>

<style>
.todo-list {
  font-family: ‘Courier New’, Courier, monospace;
  height: 100vh;
}
.todo-list__wrapper {
  color: #2c3e50;
  background-color: rgba(255, 255, 255, 0.4);
  padding: 20px;
}
.todo-list__header {
  font-weight: normal;
  margin-top: 0px;
}
.todo-list__container {
  margin: 0;
  padding: 0;
  list-style-position: inside;
}
.todo-list__delete {
  font-size: 130%;
  text-decoration: none;
  color: #2c3e50;
}
.todo-list__delete:hover {
  color: #9e0020;
}
.todo-list__new {
  margin: 20px 0px 20px 0px;
}

.todo-list__save-new {
  text-decoration: none;
  display: inline-block;
  padding: 10px 15px;
  position: relative;
  color: #2c3e50;
  border: 1px solid #2c3e50;
  background: none;
  font-weight: 300;
  text-transform: uppercase;
  letter-spacing: 2px;
}
.todo-list__save-new:hover {
  background: rgba(255, 255, 255, 0.6);
}
</style>
